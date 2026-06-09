# CPropMgr::ComposeHwndIdentityString(HWND__ *,ulong,ulong,uchar * *,ulong *)

- ea: `0x180018c60`
- end: `0x180018d5a`
- name: `?ComposeHwndIdentityString@CPropMgr@@UEAAJPEAUHWND__@@KKPEAPEAEPEAK@Z`
- size: `250`
- prototype: `__int64 __fastcall(CPropMgr *__hidden this, HWND, unsigned int, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180018c60`
- `0x180023f3c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018ca4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018ca4`

## pseudocode

```c
__int64 __fastcall CPropMgr::ComposeHwndIdentityString(
        CPropMgr *this,
        HWND a2,
        int a3,
        int a4,
        unsigned __int8 **a5,
        unsigned int *a6)
{
  int v8; // r15d
  char v9; // bl
  unsigned __int8 *v10; // rax
  char v11; // cl
  int v12; // r8d

  v8 = (int)a2;
  v9 = (char)this;
  if ( (Microsoft_Windows_OLEACCEnableBits & 2) != 0 )
    McTemplateMofU0qpd((_BYTE)this, (unsigned int)OLEACC_ClientApiCall_Start, a3, 1008, (char)this, 0);
  *a5 = 0;
  *a6 = 0;
  v10 = (unsigned __int8 *)CoTaskMemAlloc(0x10u);
  if ( v10 )
  {
    *(_DWORD *)v10 = -2147483647;
    *((_DWORD *)v10 + 1) = v8;
    *((_DWORD *)v10 + 2) = a3;
    *((_DWORD *)v10 + 3) = a4;
    *a5 = v10;
    *a6 = 16;
    if ( (Microsoft_Windows_OLEACCEnableBits & 2) != 0 )
      McTemplateMofU0qpd(v11, (unsigned int)OLEACC_ClientApiCall_Stop, v12, 1008, v9, 0);
    return 0;
  }
  else
  {
    if ( (Microsoft_Windows_OLEACCEnableBits & 2) != 0 )
      McTemplateMofU0qpd(v11, (unsigned int)OLEACC_ClientApiCall_Stop, v12, 1008, v9, 0);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180018c60  push    rbx
0x180018c62  push    rbp
0x180018c63  push    rsi
0x180018c64  push    rdi
0x180018c65  push    r14
0x180018c67  push    r15
0x180018c69  sub     rsp, 38h
0x180018c6d  test    byte ptr cs:Microsoft_Windows_OLEACCEnableBits, 2
0x180018c74  mov     ebp, r9d
0x180018c77  mov     r14d, r8d
0x180018c7a  mov     r15, rdx
0x180018c7d  mov     rbx, rcx
0x180018c80  jnz     short loc_180018CF1
0x180018c82  mov     rdi, [rsp+68h+arg_20]
0x180018c8a  mov     ecx, 10h; cb
0x180018c8f  mov     rsi, [rsp+68h+arg_28]
0x180018c97  mov     qword ptr [rdi], 0
0x180018c9e  mov     dword ptr [rsi], 0
0x180018ca4  call    cs:__imp_CoTaskMemAlloc
0x180018caa  test    rax, rax
0x180018cad  jz      short loc_180018CE1
0x180018caf  mov     dword ptr [rax], 80000001h
0x180018cb5  mov     [rax+4], r15d
0x180018cb9  mov     [rax+8], r14d
0x180018cbd  mov     [rax+0Ch], ebp
0x180018cc0  mov     [rdi], rax
0x180018cc3  mov     dword ptr [rsi], 10h
0x180018cc9  test    byte ptr cs:Microsoft_Windows_OLEACCEnableBits, 2
0x180018cd0  jnz     short loc_180018D36
0x180018cd2  xor     eax, eax
0x180018cd4  add     rsp, 38h
0x180018cd8  pop     r15
0x180018cda  pop     r14
0x180018cdc  pop     rdi
0x180018cdd  pop     rsi
0x180018cde  pop     rbp
0x180018cdf  pop     rbx
0x180018ce0  retn
0x180018ce1  test    byte ptr cs:Microsoft_Windows_OLEACCEnableBits, 2
0x180018ce8  jnz     short loc_180018D15
0x180018cea  mov     eax, 8007000Eh
0x180018cef  jmp     short loc_180018CD4
0x180018cf1  mov     [rsp+68h+var_40], 0
0x180018cf9  lea     rdx, OLEACC_ClientApiCall_Start
0x180018d00  mov     r9d, 3F0h
0x180018d06  mov     [rsp+68h+var_48], rbx
0x180018d0b  call    McTemplateMofU0qpd
0x180018d10  jmp     loc_180018C82
0x180018d15  mov     [rsp+68h+var_40], 0
0x180018d1d  lea     rdx, OLEACC_ClientApiCall_Stop
0x180018d24  mov     r9d, 3F0h
0x180018d2a  mov     [rsp+68h+var_48], rbx
0x180018d2f  call    McTemplateMofU0qpd
0x180018d34  jmp     short loc_180018CEA
0x180018d36  mov     [rsp+68h+var_40], 0
0x180018d3e  lea     rdx, OLEACC_ClientApiCall_Stop
0x180018d45  mov     r9d, 3F0h
0x180018d4b  mov     [rsp+68h+var_48], rbx
0x180018d50  call    McTemplateMofU0qpd
0x180018d55  jmp     loc_180018CD2
```
