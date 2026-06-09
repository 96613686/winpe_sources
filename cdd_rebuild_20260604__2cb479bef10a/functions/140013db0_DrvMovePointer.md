# DrvMovePointer

- ea: `0x140013db0`
- end: `0x140013f52`
- name: `DrvMovePointer`
- size: `418`
- prototype: `FN_DrvMovePointer`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140013db0`
- `0x1400371f0`
- `0x1400372d0`

## import_xrefs

- `watchdog!WdLogSingleEntry2` at `0x140013e63`
- `watchdog!WdLogSingleEntry2` at `0x140013f04`
- `watchdog!WdLogSingleEntry2` at `0x140013e63`
- `watchdog!WdLogSingleEntry2` at `0x140013f04`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x140013e79`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x140013f1a`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x140013e79`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x140013f1a`

## pseudocode

```c
void __stdcall DrvMovePointer(SURFOBJ *pso, LONG x, LONG y, RECTL *prcl)
{
  DHPDEV dhpdev; // rbx
  int v5; // edx
  unsigned int v6; // r8d
  __int64 v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  _QWORD *v10; // rax
  __int64 v11; // r8
  __int64 v12; // rax
  int v13; // eax
  _QWORD *v14; // rax
  int v15; // [rsp+20h] [rbp-28h] BYREF
  int v16; // [rsp+24h] [rbp-24h]
  __int64 v17; // [rsp+28h] [rbp-20h]

  if ( y >= 0 || x < 0 )
  {
    dhpdev = pso->dhpdev;
    if ( x == -1 )
    {
      v11 = *((unsigned __int8 *)dhpdev + 1120);
      v15 = *((_DWORD *)dhpdev + 288);
      v12 = *((_QWORD *)dhpdev + 152);
      v17 = 0;
      v16 = 0;
      v13 = (*(__int64 (__fastcall **)(_QWORD, int *, __int64, RECTL *))(v12 + 136))(
              *((_QWORD *)dhpdev + 153),
              &v15,
              v11,
              prcl);
      if ( v13 < 0 )
      {
        WdLogSingleEntry2(3, v13, *((_QWORD *)dhpdev + 153));
        WdLogGlobalForLineNumber = 81;
        v14 = (_QWORD *)WdLogNewEntry5_WdWarning();
        v14[3] = gCddImageInfo;
        v14[4] = (unsigned int)dword_14003E570;
        v14[5] = 215857758;
        WdLogGlobalForLineNumber = 81;
      }
    }
    else if ( *((_BYTE *)dhpdev + 1132) )
    {
      v5 = x - *((_DWORD *)dhpdev + 281);
      v6 = y - *((_DWORD *)dhpdev + 282);
      v7 = *((_QWORD *)dhpdev + 153);
      v15 = *((_DWORD *)dhpdev + 288);
      v8 = *((_QWORD *)dhpdev + 152);
      v16 = v5;
      v17 = v6 | 0x100000000LL;
      v9 = (*(__int64 (__fastcall **)(__int64, int *, _QWORD, RECTL *))(v8 + 136))(
             v7,
             &v15,
             *((unsigned __int8 *)dhpdev + 1120),
             prcl);
      if ( v9 < 0 )
      {
        WdLogSingleEntry2(3, v9, *((_QWORD *)dhpdev + 153));
        WdLogGlobalForLineNumber = 102;
        v10 = (_QWORD *)WdLogNewEntry5_WdWarning();
        v10[3] = gCddImageInfo;
        v10[4] = (unsigned int)dword_14003E570;
        v10[5] = 215857758;
        WdLogGlobalForLineNumber = 102;
      }
    }
  }
}

```

## disassembly

```asm
0x140013db0  sub     rsp, 48h
0x140013db4  mov     rax, cs:__security_cookie
0x140013dbb  xor     rax, rsp
0x140013dbe  mov     [rsp+48h+var_18], rax
0x140013dc3  test    r8d, r8d
0x140013dc6  js      short loc_140013DFB
0x140013dc8  mov     [rsp+48h+var_8], rbx
0x140013dcd  mov     rbx, [rcx+10h]
0x140013dd1  cmp     edx, 0FFFFFFFFh
0x140013dd4  jz      loc_140013EB1
0x140013dda  cmp     byte ptr [rbx+46Ch], 0
0x140013de1  jnz     short loc_140013E01
0x140013de3  mov     rbx, [rsp+48h+var_8]
0x140013de8  mov     rcx, [rsp+48h+var_18]
0x140013ded  xor     rcx, rsp; StackCookie
0x140013df0  call    __security_check_cookie
0x140013df5  add     rsp, 48h
0x140013df9  retn
0x140013dfb  test    edx, edx
0x140013dfd  js      short loc_140013DC8
0x140013dff  jmp     short loc_140013DE8
0x140013e01  mov     eax, [rbx+480h]
0x140013e07  sub     edx, [rbx+464h]
0x140013e0d  sub     r8d, [rbx+468h]
0x140013e14  mov     rcx, [rbx+4C8h]
0x140013e1b  mov     [rsp+48h+var_28], eax
0x140013e1f  mov     rax, [rbx+4C0h]
0x140013e26  mov     [rsp+48h+var_24], edx
0x140013e2a  lea     rdx, [rsp+48h+var_28]
0x140013e2f  mov     dword ptr [rsp+48h+var_20], r8d
0x140013e34  movzx   r8d, byte ptr [rbx+460h]
0x140013e3c  mov     dword ptr [rsp+48h+var_20+4], 1
0x140013e44  mov     rax, [rax+88h]
0x140013e4b  call    _guard_dispatch_icall
0x140013e50  test    eax, eax
0x140013e52  jns     short loc_140013DE3
0x140013e54  mov     r8, [rbx+4C8h]
0x140013e5b  mov     ecx, 3
0x140013e60  movsxd  rdx, eax
0x140013e63  call    cs:__imp_WdLogSingleEntry2
0x140013e6a  nop     dword ptr [rax+rax+00h]
0x140013e6f  mov     cs:WdLogGlobalForLineNumber, 66h ; 'f'
0x140013e79  call    cs:__imp_WdLogNewEntry5_WdWarning
0x140013e80  nop     dword ptr [rax+rax+00h]
0x140013e85  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140013e8c  mov     [rax+18h], rcx
0x140013e90  mov     ecx, cs:dword_14003E570
0x140013e96  mov     [rax+20h], rcx
0x140013e9a  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140013ea2  mov     cs:WdLogGlobalForLineNumber, 66h ; 'f'
0x140013eac  jmp     loc_140013DE3
0x140013eb1  mov     eax, [rbx+480h]
0x140013eb7  lea     rdx, [rsp+48h+var_28]
0x140013ebc  movzx   r8d, byte ptr [rbx+460h]
0x140013ec4  xor     ecx, ecx
0x140013ec6  mov     [rsp+48h+var_28], eax
0x140013eca  mov     rax, [rbx+4C0h]
0x140013ed1  mov     [rsp+48h+var_20], rcx
0x140013ed6  mov     [rsp+48h+var_24], ecx
0x140013eda  mov     rcx, [rbx+4C8h]
0x140013ee1  mov     rax, [rax+88h]
0x140013ee8  call    _guard_dispatch_icall
0x140013eed  test    eax, eax
0x140013eef  jns     loc_140013DE3
0x140013ef5  mov     r8, [rbx+4C8h]
0x140013efc  mov     ecx, 3
0x140013f01  movsxd  rdx, eax
0x140013f04  call    cs:__imp_WdLogSingleEntry2
0x140013f0b  nop     dword ptr [rax+rax+00h]
0x140013f10  mov     cs:WdLogGlobalForLineNumber, 51h ; 'Q'
0x140013f1a  call    cs:__imp_WdLogNewEntry5_WdWarning
0x140013f21  nop     dword ptr [rax+rax+00h]
0x140013f26  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140013f2d  mov     [rax+18h], rcx
0x140013f31  mov     ecx, cs:dword_14003E570
0x140013f37  mov     [rax+20h], rcx
0x140013f3b  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140013f43  mov     cs:WdLogGlobalForLineNumber, 51h ; 'Q'
0x140013f4d  jmp     loc_140013DE3
```
