# CRdpWindowTracker::ConvertHrgnToRdpRegionUsingBuffer(HRGN__ *,_RDPGFX_REGION *)

- ea: `0x14005ba0c`
- end: `0x14005bbe3`
- name: `?ConvertHrgnToRdpRegionUsingBuffer@CRdpWindowTracker@@AEAAJPEAUHRGN__@@PEAU_RDPGFX_REGION@@@Z`
- size: `471`
- prototype: `int(CRdpWindowTracker *__hidden this, HRGN, struct _RDPGFX_REGION *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x14005c7f0`
- `0x14005cdf0`

## callees

- `0x140004b1c`
- `0x1400056c4`
- `0x140005750`
- `0x14005ba0c`
- `0x14006a0e2`
- `0x14006a120`

## import_xrefs

- `USER32!CopyRect` at `0x14005bb35`
- `USER32!CopyRect` at `0x14005bbb5`
- `USER32!CopyRect` at `0x14005bbc4`
- `USER32!CopyRect` at `0x14005bb35`
- `USER32!CopyRect` at `0x14005bbb5`
- `USER32!CopyRect` at `0x14005bbc4`
- `GDI32!GetRegionData` at `0x14005bac2`
- `GDI32!GetRegionData` at `0x14005bac2`
- `GDI32!GetRgnBox` at `0x14005ba3c`
- `GDI32!GetRgnBox` at `0x14005ba3c`

## pseudocode

```c
__int64 __fastcall CRdpWindowTracker::ConvertHrgnToRdpRegionUsingBuffer(
        LPRGNDATA *this,
        HRGN a2,
        struct _RDPGFX_REGION *a3)
{
  unsigned int v6; // ebx
  unsigned int v7; // eax
  int v8; // edx
  const char *v9; // rcx
  DWORD RegionData; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  struct tagRECT rc; // [rsp+30h] [rbp-38h] BYREF

  rc = 0;
  if ( GetRgnBox(a2, &rc) )
  {
    RegionData = GetRegionData(a2, 0x424u, this[35]);
    if ( RegionData )
    {
      if ( RegionData > 0x424 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            118,
            &WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
            CurrentThreadActivityIdPrefix);
        }
        *(_DWORD *)a3 = 1;
        *((_DWORD *)a3 + 1) = 1;
        CopyRect((LPRECT)((char *)a3 + 8), &rc);
        CopyRect((LPRECT)((char *)a3 + 24), &rc);
      }
      else
      {
        *(_DWORD *)a3 = this[35]->rdh.nCount;
        *((_DWORD *)a3 + 1) = 1;
        CopyRect((LPRECT)((char *)a3 + 8), &rc);
        memcpy_0((char *)a3 + 24, this[35]->Buffer, 16LL * this[35]->rdh.nCount);
      }
      return 0;
    }
    else
    {
      v6 = -2147467259;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v7 = RdpWppGetCurrentThreadActivityIdPrefix();
        v8 = 117;
        v9 = "GetRegionData() failed";
        goto LABEL_6;
      }
    }
  }
  else
  {
    v6 = -2147467259;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
      v8 = 116;
      v9 = "GetRgnBox() failed";
LABEL_6:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v8,
        (unsigned int)&WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
        v7,
        (__int64)v9,
        -2147467259);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x14005ba0c  push    rbx
0x14005ba0e  push    rsi
0x14005ba0f  push    rdi
0x14005ba10  sub     rsp, 50h
0x14005ba14  mov     rax, cs:__security_cookie
0x14005ba1b  xor     rax, rsp
0x14005ba1e  mov     [rsp+68h+var_28], rax
0x14005ba23  mov     rsi, rdx
0x14005ba26  mov     rdi, rcx
0x14005ba29  xorps   xmm0, xmm0
0x14005ba2c  lea     rdx, [rsp+68h+rc]; lprc
0x14005ba31  mov     rcx, rsi; hrgn
0x14005ba34  mov     rbx, r8
0x14005ba37  movups  xmmword ptr [rsp+68h+rc.left], xmm0
0x14005ba3c  call    cs:__imp_GetRgnBox
0x14005ba42  test    eax, eax
0x14005ba44  jnz     short loc_14005BAB3
0x14005ba46  mov     ebx, 80004005h
0x14005ba4b  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ba52  lea     rax, WPP_GLOBAL_Control
0x14005ba59  cmp     rcx, rax
0x14005ba5c  jz      loc_14005BBCC
0x14005ba62  test    byte ptr [rcx+1Ch], 8
0x14005ba66  jz      loc_14005BBCC
0x14005ba6c  cmp     byte ptr [rcx+19h], 2
0x14005ba70  jb      loc_14005BBCC
0x14005ba76  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005ba7b  mov     edx, 74h ; 't'
0x14005ba80  lea     rcx, aGetrgnboxFaile; "GetRgnBox() failed"
0x14005ba87  mov     [rsp+68h+var_40], 80004005h
0x14005ba8f  lea     r8, WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids
0x14005ba96  mov     [rsp+68h+var_48], rcx
0x14005ba9b  mov     r9d, eax
0x14005ba9e  mov     rcx, cs:WPP_GLOBAL_Control
0x14005baa5  mov     rcx, [rcx+10h]
0x14005baa9  call    WPP_SF_DsD
0x14005baae  jmp     loc_14005BBCC
0x14005bab3  mov     r8, [rdi+118h]; lpRgnData
0x14005baba  mov     edx, 424h; nCount
0x14005babf  mov     rcx, rsi; hrgn
0x14005bac2  call    cs:__imp_GetRegionData
0x14005bac8  test    eax, eax
0x14005baca  jnz     short loc_14005BB12
0x14005bacc  mov     ebx, 80004005h
0x14005bad1  mov     rcx, cs:WPP_GLOBAL_Control
0x14005bad8  lea     rax, WPP_GLOBAL_Control
0x14005badf  cmp     rcx, rax
0x14005bae2  jz      loc_14005BBCC
0x14005bae8  test    byte ptr [rcx+1Ch], 8
0x14005baec  jz      loc_14005BBCC
0x14005baf2  cmp     byte ptr [rcx+19h], 2
0x14005baf6  jb      loc_14005BBCC
0x14005bafc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005bb01  mov     edx, 75h ; 'u'
0x14005bb06  lea     rcx, aGetregiondataF; "GetRegionData() failed"
0x14005bb0d  jmp     loc_14005BA87
0x14005bb12  cmp     eax, 424h
0x14005bb17  ja      short loc_14005BB59
0x14005bb19  mov     rax, [rdi+118h]
0x14005bb20  lea     rdx, [rsp+68h+rc]; lprcSrc
0x14005bb25  mov     ecx, [rax+8]
0x14005bb28  mov     [rbx], ecx
0x14005bb2a  lea     rcx, [rbx+8]; lprcDst
0x14005bb2e  mov     dword ptr [rbx+4], 1
0x14005bb35  call    cs:__imp_CopyRect
0x14005bb3b  mov     rdx, [rdi+118h]
0x14005bb42  lea     rcx, [rbx+18h]; void *
0x14005bb46  mov     r8d, [rdx+8]
0x14005bb4a  add     rdx, 20h ; ' '; Src
0x14005bb4e  shl     r8, 4; Size
0x14005bb52  call    memcpy_0
0x14005bb57  jmp     short loc_14005BBCA
0x14005bb59  mov     rcx, cs:WPP_GLOBAL_Control
0x14005bb60  lea     rax, WPP_GLOBAL_Control
0x14005bb67  cmp     rcx, rax
0x14005bb6a  jz      short loc_14005BB9F
0x14005bb6c  test    dword ptr [rcx+1Ch], 200h
0x14005bb73  jz      short loc_14005BB9F
0x14005bb75  cmp     byte ptr [rcx+19h], 3
0x14005bb79  jb      short loc_14005BB9F
0x14005bb7b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005bb80  mov     rcx, cs:WPP_GLOBAL_Control
0x14005bb87  lea     r8, WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids
0x14005bb8e  mov     edx, 76h ; 'v'
0x14005bb93  mov     r9d, eax
0x14005bb96  mov     rcx, [rcx+10h]
0x14005bb9a  call    WPP_SF_d
0x14005bb9f  lea     rcx, [rbx+8]; lprcDst
0x14005bba3  mov     dword ptr [rbx], 1
0x14005bba9  lea     rdx, [rsp+68h+rc]; lprcSrc
0x14005bbae  mov     dword ptr [rbx+4], 1
0x14005bbb5  call    cs:__imp_CopyRect
0x14005bbbb  lea     rcx, [rbx+18h]; lprcDst
0x14005bbbf  lea     rdx, [rsp+68h+rc]; lprcSrc
0x14005bbc4  call    cs:__imp_CopyRect
0x14005bbca  xor     ebx, ebx
0x14005bbcc  mov     eax, ebx
0x14005bbce  mov     rcx, [rsp+68h+var_28]
0x14005bbd3  xor     rcx, rsp; StackCookie
0x14005bbd6  call    __security_check_cookie
0x14005bbdb  add     rsp, 50h
0x14005bbdf  pop     rdi
0x14005bbe0  pop     rsi
0x14005bbe1  pop     rbx
0x14005bbe2  retn
```
