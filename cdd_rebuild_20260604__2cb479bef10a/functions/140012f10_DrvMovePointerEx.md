# DrvMovePointerEx

- ea: `0x140012f10`
- end: `0x1400130c7`
- name: `DrvMovePointerEx`
- size: `439`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140012f10`
- `0x1400371f0`
- `0x1400372d0`

## import_xrefs

- `watchdog!WdLogSingleEntry2` at `0x140012fd0`
- `watchdog!WdLogSingleEntry2` at `0x140013079`
- `watchdog!WdLogSingleEntry2` at `0x140012fd0`
- `watchdog!WdLogSingleEntry2` at `0x140013079`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x140012fe6`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x14001308f`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x140012fe6`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x14001308f`

## pseudocode

```c
__int64 __fastcall DrvMovePointerEx(__int64 a1, int a2, int a3, char a4)
{
  __int64 v4; // rbx
  int v6; // edx
  int v7; // r8d
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // r8
  int v11; // eax
  _QWORD *v12; // rax
  __int64 v13; // r8
  __int64 v14; // rcx
  __int64 v15; // rax
  int v16; // eax
  _QWORD *v17; // rax
  int v18; // [rsp+20h] [rbp-28h] BYREF
  unsigned __int64 v19; // [rsp+24h] [rbp-24h]
  int v20; // [rsp+2Ch] [rbp-1Ch]

  if ( a3 >= 0 || a2 < 0 )
  {
    v4 = *(_QWORD *)(a1 + 16);
    if ( a2 == -1 )
    {
      v13 = *(unsigned __int8 *)(v4 + 1120);
      v14 = *(_QWORD *)(v4 + 1224);
      v18 = *(_DWORD *)(v4 + 1152);
      v19 = 0;
      v15 = *(_QWORD *)(v4 + 1216);
      v20 = 2 * (a4 & 1);
      v16 = (*(__int64 (__fastcall **)(__int64, int *, __int64))(v15 + 136))(v14, &v18, v13);
      if ( v16 < 0 )
      {
        WdLogSingleEntry2(3, v16, *(_QWORD *)(v4 + 1224));
        WdLogGlobalForLineNumber = 81;
        v17 = (_QWORD *)WdLogNewEntry5_WdWarning();
        v17[3] = gCddImageInfo;
        v17[4] = (unsigned int)dword_14003E570;
        v17[5] = 215857758;
        WdLogGlobalForLineNumber = 81;
      }
    }
    else if ( *(_BYTE *)(v4 + 1132) )
    {
      v6 = a2 - *(_DWORD *)(v4 + 1124);
      v7 = a3 - *(_DWORD *)(v4 + 1128);
      v8 = *(_QWORD *)(v4 + 1224);
      v18 = *(_DWORD *)(v4 + 1152);
      v9 = *(_QWORD *)(v4 + 1216);
      v19 = __PAIR64__(v7, v6);
      v10 = *(unsigned __int8 *)(v4 + 1120);
      v20 = (2 * (a4 & 1)) | 1;
      v11 = (*(__int64 (__fastcall **)(__int64, int *, __int64))(v9 + 136))(v8, &v18, v10);
      if ( v11 < 0 )
      {
        WdLogSingleEntry2(3, v11, *(_QWORD *)(v4 + 1224));
        WdLogGlobalForLineNumber = 102;
        v12 = (_QWORD *)WdLogNewEntry5_WdWarning();
        v12[3] = gCddImageInfo;
        v12[4] = (unsigned int)dword_14003E570;
        v12[5] = 215857758;
        WdLogGlobalForLineNumber = 102;
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x140012f10  sub     rsp, 48h
0x140012f14  mov     rax, cs:__security_cookie
0x140012f1b  xor     rax, rsp
0x140012f1e  mov     [rsp+48h+var_18], rax
0x140012f23  test    r8d, r8d
0x140012f26  js      short loc_140012F60
0x140012f28  mov     [rsp+48h+var_8], rbx
0x140012f2d  mov     rbx, [rcx+10h]
0x140012f31  cmp     edx, 0FFFFFFFFh
0x140012f34  jz      loc_14001301E
0x140012f3a  cmp     byte ptr [rbx+46Ch], 0
0x140012f41  jnz     short loc_140012F66
0x140012f43  mov     rbx, [rsp+48h+var_8]
0x140012f48  mov     eax, 1
0x140012f4d  mov     rcx, [rsp+48h+var_18]
0x140012f52  xor     rcx, rsp; StackCookie
0x140012f55  call    __security_check_cookie
0x140012f5a  add     rsp, 48h
0x140012f5e  retn
0x140012f60  test    edx, edx
0x140012f62  js      short loc_140012F28
0x140012f64  jmp     short loc_140012F48
0x140012f66  mov     eax, [rbx+480h]
0x140012f6c  and     r9d, 1
0x140012f70  sub     edx, [rbx+464h]
0x140012f76  add     r9d, r9d
0x140012f79  sub     r8d, [rbx+468h]
0x140012f80  or      r9d, 1
0x140012f84  mov     rcx, [rbx+4C8h]
0x140012f8b  mov     [rsp+48h+var_28], eax
0x140012f8f  mov     rax, [rbx+4C0h]
0x140012f96  mov     dword ptr [rsp+48h+var_24], edx
0x140012f9a  lea     rdx, [rsp+48h+var_28]
0x140012f9f  mov     dword ptr [rsp+48h+var_24+4], r8d
0x140012fa4  movzx   r8d, byte ptr [rbx+460h]
0x140012fac  mov     [rsp+48h+var_1C], r9d
0x140012fb1  mov     rax, [rax+88h]
0x140012fb8  call    _guard_dispatch_icall
0x140012fbd  test    eax, eax
0x140012fbf  jns     short loc_140012F43
0x140012fc1  mov     r8, [rbx+4C8h]
0x140012fc8  mov     ecx, 3
0x140012fcd  movsxd  rdx, eax
0x140012fd0  call    cs:__imp_WdLogSingleEntry2
0x140012fd7  nop     dword ptr [rax+rax+00h]
0x140012fdc  mov     cs:WdLogGlobalForLineNumber, 66h ; 'f'
0x140012fe6  call    cs:__imp_WdLogNewEntry5_WdWarning
0x140012fed  nop     dword ptr [rax+rax+00h]
0x140012ff2  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140012ff9  mov     [rax+18h], rcx
0x140012ffd  mov     ecx, cs:dword_14003E570
0x140013003  mov     [rax+20h], rcx
0x140013007  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14001300f  mov     cs:WdLogGlobalForLineNumber, 66h ; 'f'
0x140013019  jmp     loc_140012F43
0x14001301e  mov     eax, [rbx+480h]
0x140013024  lea     rdx, [rsp+48h+var_28]
0x140013029  movzx   r8d, byte ptr [rbx+460h]
0x140013031  and     r9d, 1
0x140013035  mov     rcx, [rbx+4C8h]
0x14001303c  add     r9d, r9d
0x14001303f  mov     [rsp+48h+var_28], eax
0x140013043  xor     eax, eax
0x140013045  mov     [rsp+48h+var_24], rax
0x14001304a  mov     rax, [rbx+4C0h]
0x140013051  mov     [rsp+48h+var_1C], r9d
0x140013056  mov     rax, [rax+88h]
0x14001305d  call    _guard_dispatch_icall
0x140013062  test    eax, eax
0x140013064  jns     loc_140012F43
0x14001306a  mov     r8, [rbx+4C8h]
0x140013071  mov     ecx, 3
0x140013076  movsxd  rdx, eax
0x140013079  call    cs:__imp_WdLogSingleEntry2
0x140013080  nop     dword ptr [rax+rax+00h]
0x140013085  mov     cs:WdLogGlobalForLineNumber, 51h ; 'Q'
0x14001308f  call    cs:__imp_WdLogNewEntry5_WdWarning
0x140013096  nop     dword ptr [rax+rax+00h]
0x14001309b  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x1400130a2  mov     [rax+18h], rcx
0x1400130a6  mov     ecx, cs:dword_14003E570
0x1400130ac  mov     [rax+20h], rcx
0x1400130b0  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x1400130b8  mov     cs:WdLogGlobalForLineNumber, 51h ; 'Q'
0x1400130c2  jmp     loc_140012F43
```
