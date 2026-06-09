# CProgressBand::InitBitmaps(void)

- ea: `0x1400a6ae4`
- end: `0x1400a6c1e`
- name: `?InitBitmaps@CProgressBand@@AEAAHXZ`
- size: `314`
- prototype: `__int64 __fastcall(CProgressBand *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1400a6a58`
- `0x1400a6e98`

## callees

- `0x14000b7d8`
- `0x14000cf70`
- `0x14000d078`
- `0x140097b90`
- `0x1400a6ae4`

## import_xrefs

- `USER32!SetRect` at `0x1400a6b4d`
- `USER32!SetRect` at `0x1400a6b4d`
- `KERNEL32!GetLastError` at `0x1400a6baf`
- `KERNEL32!GetLastError` at `0x1400a6baf`
- `GDI32!GetObjectW` at `0x1400a6b2c`
- `GDI32!GetObjectW` at `0x1400a6b2c`
- `GDI32!DeleteObject` at `0x1400a6b9f`
- `GDI32!DeleteObject` at `0x1400a6b9f`

## string_xrefs

- `0x1400a6bdb`: `LoadImageFromResID failed`

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
0x1400a6ae4  mov     [rsp+arg_0], rbx
0x1400a6ae9  push    rdi
0x1400a6aea  sub     rsp, 50h
0x1400a6aee  xorps   xmm0, xmm0
0x1400a6af1  xorps   xmm1, xmm1
0x1400a6af4  movups  xmmword ptr [rcx+28h], xmm1
0x1400a6af8  movzx   edx, word ptr [rcx+1Ch]; unsigned __int16 *
0x1400a6afc  mov     rbx, rcx
0x1400a6aff  mov     rcx, [rcx+10h]; HINSTANCE
0x1400a6b03  movups  [rsp+58h+pv], xmm0
0x1400a6b08  movups  [rsp+58h+var_18], xmm0
0x1400a6b0d  call    ?LoadImageFromResID@@YAPEAUHBITMAP__@@PEAUHINSTANCE__@@PEBG@Z; LoadImageFromResID(HINSTANCE__ *,ushort const *)
0x1400a6b12  mov     [rbx+20h], rax
0x1400a6b16  test    rax, rax
0x1400a6b19  jz      loc_1400A6BAF
0x1400a6b1f  lea     r8, [rsp+58h+pv]; pv
0x1400a6b24  mov     edx, 20h ; ' '; c
0x1400a6b29  mov     rcx, rax; h
0x1400a6b2c  call    cs:__imp_GetObjectW
0x1400a6b32  cmp     eax, 20h ; ' '
0x1400a6b35  jb      short loc_1400A6B58
0x1400a6b37  mov     eax, dword ptr [rsp+58h+pv+8]
0x1400a6b3b  lea     rcx, [rbx+28h]; lprc
0x1400a6b3f  mov     r9d, dword ptr [rsp+58h+pv+4]; xRight
0x1400a6b44  xor     r8d, r8d; yTop
0x1400a6b47  xor     edx, edx; xLeft
0x1400a6b49  mov     [rsp+58h+yBottom], eax; yBottom
0x1400a6b4d  call    cs:__imp_SetRect
0x1400a6b53  jmp     loc_1400A6C0A
0x1400a6b58  mov     rax, cs:WPP_GLOBAL_Control
0x1400a6b5f  lea     rcx, WPP_GLOBAL_Control
0x1400a6b66  cmp     rax, rcx
0x1400a6b69  jz      short loc_1400A6B9B
0x1400a6b6b  test    byte ptr [rax+1Ch], 1
0x1400a6b6f  jz      short loc_1400A6B9B
0x1400a6b71  cmp     byte ptr [rax+19h], 2
0x1400a6b75  jb      short loc_1400A6B9B
0x1400a6b77  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a6b7c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a6b83  lea     r8, WPP_222c3f9ea19738b6d6405590902ee7a9_Traceguids
0x1400a6b8a  mov     edx, 0Ah
0x1400a6b8f  mov     r9d, eax
0x1400a6b92  mov     rcx, [rcx+10h]
0x1400a6b96  call    WPP_SF_d
0x1400a6b9b  mov     rcx, [rbx+20h]; ho
0x1400a6b9f  call    cs:__imp_DeleteObject
0x1400a6ba5  mov     qword ptr [rbx+20h], 0
0x1400a6bad  jmp     short loc_1400A6C0A
0x1400a6baf  call    cs:__imp_GetLastError
0x1400a6bb5  mov     edi, eax
0x1400a6bb7  mov     rdx, cs:WPP_GLOBAL_Control
0x1400a6bbe  lea     rcx, WPP_GLOBAL_Control
0x1400a6bc5  cmp     rdx, rcx
0x1400a6bc8  jz      short loc_1400A6C0A
0x1400a6bca  test    byte ptr [rdx+1Ch], 8
0x1400a6bce  jz      short loc_1400A6C0A
0x1400a6bd0  cmp     byte ptr [rdx+19h], 2
0x1400a6bd4  jb      short loc_1400A6C0A
0x1400a6bd6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a6bdb  lea     rcx, aLoadimagefromr; "LoadImageFromResID failed"
0x1400a6be2  mov     [rsp+58h+var_30], edi
0x1400a6be6  mov     qword ptr [rsp+58h+yBottom], rcx
0x1400a6beb  lea     r8, WPP_222c3f9ea19738b6d6405590902ee7a9_Traceguids
0x1400a6bf2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a6bf9  mov     edx, 0Bh
0x1400a6bfe  mov     r9d, eax
0x1400a6c01  mov     rcx, [rcx+10h]
0x1400a6c05  call    WPP_SF_DsD
0x1400a6c0a  xor     eax, eax
0x1400a6c0c  cmp     [rbx+20h], rax
0x1400a6c10  mov     rbx, [rsp+58h+arg_0]
0x1400a6c15  setnz   al
0x1400a6c18  add     rsp, 50h
0x1400a6c1c  pop     rdi
0x1400a6c1d  retn
```
