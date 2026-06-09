# CProgressBand::InitBitmaps(void)

- ea: `0x1400a4974`
- end: `0x1400a4aae`
- name: `?InitBitmaps@CProgressBand@@AEAAHXZ`
- size: `314`
- prototype: `__int64 __fastcall(CProgressBand *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1400a48e8`
- `0x1400a4d28`

## callees

- `0x14000b7d8`
- `0x14000cf70`
- `0x14000d078`
- `0x140095a20`
- `0x1400a4974`

## import_xrefs

- `USER32!SetRect` at `0x1400a49dd`
- `USER32!SetRect` at `0x1400a49dd`
- `KERNEL32!GetLastError` at `0x1400a4a3f`
- `KERNEL32!GetLastError` at `0x1400a4a3f`
- `GDI32!GetObjectW` at `0x1400a49bc`
- `GDI32!GetObjectW` at `0x1400a49bc`
- `GDI32!DeleteObject` at `0x1400a4a2f`
- `GDI32!DeleteObject` at `0x1400a4a2f`

## string_xrefs

- `0x1400a4a6b`: `LoadImageFromResID failed`

## pseudocode

```c
_BOOL8 __fastcall CProgressBand::InitBitmaps(CProgressBand *this)
{
  const unsigned __int16 *v1; // rdx
  HINSTANCE v3; // rcx
  HBITMAP ImageFromResID; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  DWORD LastError; // edi
  unsigned int v7; // eax
  DWORD v9; // [rsp+28h] [rbp-30h]
  __int128 pv; // [rsp+30h] [rbp-28h] BYREF
  __int128 v11; // [rsp+40h] [rbp-18h]

  *(_OWORD *)((char *)this + 40) = 0;
  v1 = (const unsigned __int16 *)*((unsigned __int16 *)this + 14);
  v3 = (HINSTANCE)*((_QWORD *)this + 2);
  pv = 0;
  v11 = 0;
  ImageFromResID = LoadImageFromResID(v3, v1);
  *((_QWORD *)this + 4) = ImageFromResID;
  if ( ImageFromResID )
  {
    if ( (unsigned int)GetObjectW(ImageFromResID, 32, &pv) < 0x20 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          WPP_222c3f9ea19738b6d6405590902ee7a9_Traceguids,
          CurrentThreadActivityIdPrefix);
      }
      DeleteObject(*((HGDIOBJ *)this + 4));
      *((_QWORD *)this + 4) = 0;
    }
    else
    {
      SetRect((LPRECT)((char *)this + 40), 0, 0, SDWORD1(pv), SDWORD2(pv));
    }
  }
  else
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
      v9 = LastError;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)WPP_222c3f9ea19738b6d6405590902ee7a9_Traceguids,
        v7,
        (__int64)"LoadImageFromResID failed",
        v9,
        pv,
        v11);
    }
  }
  return *((_QWORD *)this + 4) != 0;
}

```

## disassembly

```asm
0x1400a4974  mov     [rsp+arg_0], rbx
0x1400a4979  push    rdi
0x1400a497a  sub     rsp, 50h
0x1400a497e  xorps   xmm0, xmm0
0x1400a4981  xorps   xmm1, xmm1
0x1400a4984  movups  xmmword ptr [rcx+28h], xmm1
0x1400a4988  movzx   edx, word ptr [rcx+1Ch]; unsigned __int16 *
0x1400a498c  mov     rbx, rcx
0x1400a498f  mov     rcx, [rcx+10h]; HINSTANCE
0x1400a4993  movups  [rsp+58h+pv], xmm0
0x1400a4998  movups  [rsp+58h+var_18], xmm0
0x1400a499d  call    ?LoadImageFromResID@@YAPEAUHBITMAP__@@PEAUHINSTANCE__@@PEBG@Z; LoadImageFromResID(HINSTANCE__ *,ushort const *)
0x1400a49a2  mov     [rbx+20h], rax
0x1400a49a6  test    rax, rax
0x1400a49a9  jz      loc_1400A4A3F
0x1400a49af  lea     r8, [rsp+58h+pv]; pv
0x1400a49b4  mov     edx, 20h ; ' '; c
0x1400a49b9  mov     rcx, rax; h
0x1400a49bc  call    cs:__imp_GetObjectW
0x1400a49c2  cmp     eax, 20h ; ' '
0x1400a49c5  jb      short loc_1400A49E8
0x1400a49c7  mov     eax, dword ptr [rsp+58h+pv+8]
0x1400a49cb  lea     rcx, [rbx+28h]; lprc
0x1400a49cf  mov     r9d, dword ptr [rsp+58h+pv+4]; xRight
0x1400a49d4  xor     r8d, r8d; yTop
0x1400a49d7  xor     edx, edx; xLeft
0x1400a49d9  mov     [rsp+58h+yBottom], eax; yBottom
0x1400a49dd  call    cs:__imp_SetRect
0x1400a49e3  jmp     loc_1400A4A9A
0x1400a49e8  mov     rax, cs:WPP_GLOBAL_Control
0x1400a49ef  lea     rcx, WPP_GLOBAL_Control
0x1400a49f6  cmp     rax, rcx
0x1400a49f9  jz      short loc_1400A4A2B
0x1400a49fb  test    byte ptr [rax+1Ch], 1
0x1400a49ff  jz      short loc_1400A4A2B
0x1400a4a01  cmp     byte ptr [rax+19h], 2
0x1400a4a05  jb      short loc_1400A4A2B
0x1400a4a07  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a4a0c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a4a13  lea     r8, WPP_222c3f9ea19738b6d6405590902ee7a9_Traceguids
0x1400a4a1a  mov     edx, 0Ah
0x1400a4a1f  mov     r9d, eax
0x1400a4a22  mov     rcx, [rcx+10h]
0x1400a4a26  call    WPP_SF_d
0x1400a4a2b  mov     rcx, [rbx+20h]; ho
0x1400a4a2f  call    cs:__imp_DeleteObject
0x1400a4a35  mov     qword ptr [rbx+20h], 0
0x1400a4a3d  jmp     short loc_1400A4A9A
0x1400a4a3f  call    cs:__imp_GetLastError
0x1400a4a45  mov     edi, eax
0x1400a4a47  mov     rdx, cs:WPP_GLOBAL_Control
0x1400a4a4e  lea     rcx, WPP_GLOBAL_Control
0x1400a4a55  cmp     rdx, rcx
0x1400a4a58  jz      short loc_1400A4A9A
0x1400a4a5a  test    byte ptr [rdx+1Ch], 8
0x1400a4a5e  jz      short loc_1400A4A9A
0x1400a4a60  cmp     byte ptr [rdx+19h], 2
0x1400a4a64  jb      short loc_1400A4A9A
0x1400a4a66  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a4a6b  lea     rcx, aLoadimagefromr; "LoadImageFromResID failed"
0x1400a4a72  mov     [rsp+58h+var_30], edi
0x1400a4a76  mov     qword ptr [rsp+58h+yBottom], rcx
0x1400a4a7b  lea     r8, WPP_222c3f9ea19738b6d6405590902ee7a9_Traceguids
0x1400a4a82  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a4a89  mov     edx, 0Bh
0x1400a4a8e  mov     r9d, eax
0x1400a4a91  mov     rcx, [rcx+10h]
0x1400a4a95  call    WPP_SF_DsD
0x1400a4a9a  xor     eax, eax
0x1400a4a9c  cmp     [rbx+20h], rax
0x1400a4aa0  mov     rbx, [rsp+58h+arg_0]
0x1400a4aa5  setnz   al
0x1400a4aa8  add     rsp, 50h
0x1400a4aac  pop     rdi
0x1400a4aad  retn
```
