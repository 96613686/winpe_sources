# CWANPOTSLinkConfigService::GetRasEntry(tagRASENTRYW * *)

- ea: `0x18008daf4`
- end: `0x18008dc5a`
- name: `?GetRasEntry@CWANPOTSLinkConfigService@@AEAAJPEAPEAUtagRASENTRYW@@@Z`
- size: `358`
- prototype: `__int64 __fastcall(CWANPOTSLinkConfigService *__hidden this, struct tagRASENTRYW **)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18008dc60`
- `0x18008dd10`
- `0x18008dde0`

## callees

- `0x18004e0c0`
- `0x18004ed64`
- `0x18008daf4`
- `0x18008e890`
- `0x180090010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008dc0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008dc25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008dc30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008dc0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008dc25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008dc30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008dbb5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008dbb5`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasGetEntryPropertiesW` at `0x18008dba0`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasGetEntryPropertiesW` at `0x18008dbfc`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasGetEntryPropertiesW` at `0x18008dba0`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasGetEntryPropertiesW` at `0x18008dbfc`

## pseudocode

```c
__int64 __fastcall CWANPOTSLinkConfigService::GetRasEntry(CWANPOTSLinkConfigService *this, struct tagRASENTRYW **a2)
{
  __int64 v2; // rcx
  int v4; // ebx
  DWORD EntryPropertiesW; // eax
  struct tagRASENTRYW *v6; // rax
  struct tagRASENTRYW *v7; // rdi
  DWORD v9; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR v10[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v11; // [rsp+48h] [rbp-B8h]
  struct tagRASENTRYW v12; // [rsp+60h] [rbp-A0h] BYREF

  *a2 = 0;
  v2 = *((_QWORD *)this + 11);
  *(_OWORD *)v10 = 0;
  v11 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v2 + 24LL))(v2, v10);
  if ( v4 >= 0 )
  {
    memset_0(&v12.dwfOptions, 0, 0x1A40u);
    v12.dwSize = 6724;
    v9 = 6724;
    EntryPropertiesW = RasGetEntryPropertiesW(v10[0], v10[1], &v12, &v9, 0, 0);
    if ( !EntryPropertiesW || EntryPropertiesW == 603 )
    {
      v6 = (struct tagRASENTRYW *)CoTaskMemAlloc(v9);
      v7 = v6;
      if ( !v6 )
      {
        v4 = -2147024882;
        goto LABEL_10;
      }
      memset_0(v6, 0, v9);
      v7->dwSize = 6724;
      if ( !RasGetEntryPropertiesW(v10[0], v10[1], v7, &v9, 0, 0) )
      {
        *a2 = v7;
LABEL_10:
        CoTaskMemFree((LPVOID)v10[0]);
        CoTaskMemFree((LPVOID)v10[1]);
        return (unsigned int)v4;
      }
      CoTaskMemFree(v7);
    }
    v4 = -2147467259;
    goto LABEL_10;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18008daf4  mov     [rsp-8+arg_10], rbx
0x18008daf9  push    rbp
0x18008dafa  push    rsi
0x18008dafb  push    rdi
0x18008dafc  lea     rbp, [rsp-19C0h]
0x18008db04  mov     eax, 1AC0h
0x18008db09  call    _alloca_probe
0x18008db0e  sub     rsp, rax
0x18008db11  mov     rax, cs:__security_cookie
0x18008db18  xor     rax, rsp
0x18008db1b  mov     [rbp+19D0h+var_20], rax
0x18008db22  mov     qword ptr [rdx], 0
0x18008db29  xorps   xmm0, xmm0
0x18008db2c  mov     rcx, [rcx+58h]
0x18008db30  mov     rsi, rdx
0x18008db33  movups  xmmword ptr [rsp+1AD0h+var_1A98], xmm0
0x18008db38  lea     rdx, [rsp+1AD0h+var_1A98]
0x18008db3d  movups  [rsp+1AD0h+var_1A88], xmm0
0x18008db42  mov     rax, [rcx]
0x18008db45  mov     rax, [rax+18h]
0x18008db49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008db4e  mov     ebx, eax
0x18008db50  test    eax, eax
0x18008db52  js      loc_18008DC36
0x18008db58  xor     edx, edx; Val
0x18008db5a  lea     rcx, [rsp+1AD0h+var_1A70.dwfOptions]; void *
0x18008db5f  mov     r8d, 1A40h; Size
0x18008db65  call    memset_0
0x18008db6a  mov     rdx, [rsp+1AD0h+var_1A98+8]; LPCWSTR
0x18008db6f  lea     r9, [rsp+1AD0h+var_1AA0]; LPDWORD
0x18008db74  mov     rcx, [rsp+1AD0h+var_1A98]; LPCWSTR
0x18008db79  lea     r8, [rsp+1AD0h+var_1A70]; struct tagRASENTRYW *
0x18008db7e  mov     [rsp+1AD0h+var_1AA8], 0; LPDWORD
0x18008db87  mov     [rsp+1AD0h+var_1A70.dwSize], 1A44h
0x18008db8f  mov     [rsp+1AD0h+var_1AA0], 1A44h
0x18008db97  mov     [rsp+1AD0h+var_1AB0], 0; LPBYTE
0x18008dba0  call    cs:__imp_RasGetEntryPropertiesW
0x18008dba6  test    eax, eax
0x18008dba8  jz      short loc_18008DBB1
0x18008dbaa  cmp     eax, 25Bh
0x18008dbaf  jnz     short loc_18008DC14
0x18008dbb1  mov     ecx, [rsp+1AD0h+var_1AA0]; cb
0x18008dbb5  call    cs:__imp_CoTaskMemAlloc
0x18008dbbb  mov     rdi, rax
0x18008dbbe  test    rax, rax
0x18008dbc1  jz      short loc_18008DC1B
0x18008dbc3  mov     r8d, [rsp+1AD0h+var_1AA0]; Size
0x18008dbc8  xor     edx, edx; Val
0x18008dbca  mov     rcx, rax; void *
0x18008dbcd  call    memset_0
0x18008dbd2  mov     dword ptr [rdi], 1A44h
0x18008dbd8  lea     r9, [rsp+1AD0h+var_1AA0]; LPDWORD
0x18008dbdd  mov     rdx, [rsp+1AD0h+var_1A98+8]; LPCWSTR
0x18008dbe2  mov     r8, rdi; struct tagRASENTRYW *
0x18008dbe5  mov     rcx, [rsp+1AD0h+var_1A98]; LPCWSTR
0x18008dbea  mov     [rsp+1AD0h+var_1AA8], 0; LPDWORD
0x18008dbf3  mov     [rsp+1AD0h+var_1AB0], 0; LPBYTE
0x18008dbfc  call    cs:__imp_RasGetEntryPropertiesW
0x18008dc02  test    eax, eax
0x18008dc04  jnz     short loc_18008DC0B
0x18008dc06  mov     [rsi], rdi
0x18008dc09  jmp     short loc_18008DC20
0x18008dc0b  mov     rcx, rdi; pv
0x18008dc0e  call    cs:__imp_CoTaskMemFree
0x18008dc14  mov     ebx, 80004005h
0x18008dc19  jmp     short loc_18008DC20
0x18008dc1b  mov     ebx, 8007000Eh
0x18008dc20  mov     rcx, [rsp+1AD0h+var_1A98]; pv
0x18008dc25  call    cs:__imp_CoTaskMemFree
0x18008dc2b  mov     rcx, [rsp+1AD0h+var_1A98+8]; pv
0x18008dc30  call    cs:__imp_CoTaskMemFree
0x18008dc36  mov     eax, ebx
0x18008dc38  mov     rcx, [rbp+19D0h+var_20]
0x18008dc3f  xor     rcx, rsp; StackCookie
0x18008dc42  call    __security_check_cookie
0x18008dc47  mov     rbx, [rsp+1AD0h+arg_10]
0x18008dc4f  add     rsp, 1AC0h
0x18008dc56  pop     rdi
0x18008dc57  pop     rsi
0x18008dc58  pop     rbp
0x18008dc59  retn
```
