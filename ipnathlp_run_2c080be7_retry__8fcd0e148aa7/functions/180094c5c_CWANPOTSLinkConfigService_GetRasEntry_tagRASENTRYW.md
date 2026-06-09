# CWANPOTSLinkConfigService::GetRasEntry(tagRASENTRYW * *)

- ea: `0x180094c5c`
- end: `0x180094de7`
- name: `?GetRasEntry@CWANPOTSLinkConfigService@@AEAAJPEAPEAUtagRASENTRYW@@@Z`
- size: `395`
- prototype: `__int64 __fastcall(CWANPOTSLinkConfigService *__hidden this, struct tagRASENTRYW **)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180094df0`
- `0x180094ea0`
- `0x180094f80`

## callees

- `0x180051f30`
- `0x180052bf4`
- `0x180094c5c`
- `0x180095ab0`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180094d88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180094da5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180094db6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180094d88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180094da5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180094db6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180094d23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180094d23`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasGetEntryPropertiesW` at `0x180094d08`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasGetEntryPropertiesW` at `0x180094d70`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasGetEntryPropertiesW` at `0x180094d08`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasGetEntryPropertiesW` at `0x180094d70`

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
0x180094c5c  mov     [rsp-8+arg_10], rbx
0x180094c61  push    rbp
0x180094c62  push    rsi
0x180094c63  push    rdi
0x180094c64  lea     rbp, [rsp-19C0h]
0x180094c6c  mov     eax, 1AC0h
0x180094c71  call    _alloca_probe
0x180094c76  sub     rsp, rax
0x180094c79  mov     rax, cs:__security_cookie
0x180094c80  xor     rax, rsp
0x180094c83  mov     [rbp+19D0h+var_20], rax
0x180094c8a  mov     qword ptr [rdx], 0
0x180094c91  xorps   xmm0, xmm0
0x180094c94  mov     rcx, [rcx+58h]
0x180094c98  mov     rsi, rdx
0x180094c9b  movups  xmmword ptr [rsp+1AD0h+var_1A98], xmm0
0x180094ca0  lea     rdx, [rsp+1AD0h+var_1A98]
0x180094ca5  movups  [rsp+1AD0h+var_1A88], xmm0
0x180094caa  mov     rax, [rcx]
0x180094cad  mov     rax, [rax+18h]
0x180094cb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094cb6  mov     ebx, eax
0x180094cb8  test    eax, eax
0x180094cba  js      loc_180094DC2
0x180094cc0  xor     edx, edx; Val
0x180094cc2  lea     rcx, [rsp+1AD0h+var_1A70.dwfOptions]; void *
0x180094cc7  mov     r8d, 1A40h; Size
0x180094ccd  call    memset_0
0x180094cd2  mov     rdx, [rsp+1AD0h+var_1A98+8]; LPCWSTR
0x180094cd7  lea     r9, [rsp+1AD0h+var_1AA0]; LPDWORD
0x180094cdc  mov     rcx, [rsp+1AD0h+var_1A98]; LPCWSTR
0x180094ce1  lea     r8, [rsp+1AD0h+var_1A70]; struct tagRASENTRYW *
0x180094ce6  mov     [rsp+1AD0h+var_1AA8], 0; LPDWORD
0x180094cef  mov     [rsp+1AD0h+var_1A70.dwSize], 1A44h
0x180094cf7  mov     [rsp+1AD0h+var_1AA0], 1A44h
0x180094cff  mov     [rsp+1AD0h+var_1AB0], 0; LPBYTE
0x180094d08  call    cs:__imp_RasGetEntryPropertiesW
0x180094d0f  nop     dword ptr [rax+rax+00h]
0x180094d14  test    eax, eax
0x180094d16  jz      short loc_180094D1F
0x180094d18  cmp     eax, 25Bh
0x180094d1d  jnz     short loc_180094D94
0x180094d1f  mov     ecx, [rsp+1AD0h+var_1AA0]; cb
0x180094d23  call    cs:__imp_CoTaskMemAlloc
0x180094d2a  nop     dword ptr [rax+rax+00h]
0x180094d2f  mov     rdi, rax
0x180094d32  test    rax, rax
0x180094d35  jz      short loc_180094D9B
0x180094d37  mov     r8d, [rsp+1AD0h+var_1AA0]; Size
0x180094d3c  xor     edx, edx; Val
0x180094d3e  mov     rcx, rax; void *
0x180094d41  call    memset_0
0x180094d46  mov     dword ptr [rdi], 1A44h
0x180094d4c  lea     r9, [rsp+1AD0h+var_1AA0]; LPDWORD
0x180094d51  mov     rdx, [rsp+1AD0h+var_1A98+8]; LPCWSTR
0x180094d56  mov     r8, rdi; struct tagRASENTRYW *
0x180094d59  mov     rcx, [rsp+1AD0h+var_1A98]; LPCWSTR
0x180094d5e  mov     [rsp+1AD0h+var_1AA8], 0; LPDWORD
0x180094d67  mov     [rsp+1AD0h+var_1AB0], 0; LPBYTE
0x180094d70  call    cs:__imp_RasGetEntryPropertiesW
0x180094d77  nop     dword ptr [rax+rax+00h]
0x180094d7c  test    eax, eax
0x180094d7e  jnz     short loc_180094D85
0x180094d80  mov     [rsi], rdi
0x180094d83  jmp     short loc_180094DA0
0x180094d85  mov     rcx, rdi; pv
0x180094d88  call    cs:__imp_CoTaskMemFree
0x180094d8f  nop     dword ptr [rax+rax+00h]
0x180094d94  mov     ebx, 80004005h
0x180094d99  jmp     short loc_180094DA0
0x180094d9b  mov     ebx, 8007000Eh
0x180094da0  mov     rcx, [rsp+1AD0h+var_1A98]; pv
0x180094da5  call    cs:__imp_CoTaskMemFree
0x180094dac  nop     dword ptr [rax+rax+00h]
0x180094db1  mov     rcx, [rsp+1AD0h+var_1A98+8]; pv
0x180094db6  call    cs:__imp_CoTaskMemFree
0x180094dbd  nop     dword ptr [rax+rax+00h]
0x180094dc2  mov     eax, ebx
0x180094dc4  mov     rcx, [rbp+19D0h+var_20]
0x180094dcb  xor     rcx, rsp; StackCookie
0x180094dce  call    __security_check_cookie
0x180094dd3  mov     rbx, [rsp+1AD0h+arg_10]
0x180094ddb  add     rsp, 1AC0h
0x180094de2  pop     rdi
0x180094de3  pop     rsi
0x180094de4  pop     rbp
0x180094de5  retn
```
