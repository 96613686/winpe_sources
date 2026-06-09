# GetRasEntryProperties(ushort const *,ushort const *,tagRASENTRYW * *)

- ea: `0x18000beb8`
- end: `0x18000bff9`
- name: `?GetRasEntryProperties@@YAJPEBG0PEAPEAUtagRASENTRYW@@@Z`
- size: `321`
- prototype: `__int64 __fastcall(LPCWSTR, LPCWSTR, struct tagRASENTRYW **)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009630`
- `0x180009e60`
- `0x18000ad60`

## callees

- `0x18000beb8`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000bf0b`
- `KERNEL32!SetLastError` at `0x18000bf0b`
- `RASAPI32!RasGetEntryPropertiesW` at `0x18000bf47`
- `RASAPI32!RasGetEntryPropertiesW` at `0x18000bfa9`
- `RASAPI32!RasGetEntryPropertiesW` at `0x18000bf47`
- `RASAPI32!RasGetEntryPropertiesW` at `0x18000bfa9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bef2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bf6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bef2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bf6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bf5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bfc3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bf5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bfc3`

## pseudocode

```c
__int64 __fastcall GetRasEntryProperties(LPCWSTR a1, LPCWSTR a2, struct tagRASENTRYW **a3)
{
  struct tagRASENTRYW *v6; // rdi
  signed int EntryPropertiesW; // ebx
  struct tagRASENTRYW *v8; // rax
  DWORD v10; // [rsp+58h] [rbp+10h] BYREF

  if ( !a2 || !a3 )
    return (unsigned int)-2147024809;
  v10 = 6724;
  v6 = (struct tagRASENTRYW *)CoTaskMemAlloc(0x1A44u);
  if ( !v6 )
    goto LABEL_4;
  v6->dwSize = v10;
  EntryPropertiesW = RasGetEntryPropertiesW(a1, a2, v6, &v10, 0, 0);
  if ( EntryPropertiesW == 603 )
  {
    CoTaskMemFree(v6);
    v8 = (struct tagRASENTRYW *)CoTaskMemAlloc(v10);
    v6 = v8;
    if ( !v8 )
    {
LABEL_4:
      SetLastError(8u);
      return (unsigned int)-2147024888;
    }
    v8->dwSize = 6724;
    EntryPropertiesW = RasGetEntryPropertiesW(a1, a2, v8, &v10, 0, 0);
  }
  if ( EntryPropertiesW )
  {
    CoTaskMemFree(v6);
    if ( EntryPropertiesW > 0 )
      return (unsigned __int16)EntryPropertiesW | 0x80070000;
  }
  else
  {
    *a3 = v6;
  }
  return (unsigned int)EntryPropertiesW;
}

```

## disassembly

```asm
0x18000beb8  mov     [rsp+arg_0], rbx
0x18000bebd  mov     [rsp+arg_10], rbp
0x18000bec2  push    rsi
0x18000bec3  push    rdi
0x18000bec4  push    r14
0x18000bec6  sub     rsp, 30h
0x18000beca  mov     rsi, r8
0x18000becd  mov     rbp, rdx
0x18000bed0  mov     r14, rcx
0x18000bed3  test    rdx, rdx
0x18000bed6  jz      loc_18000BFDE
0x18000bedc  test    r8, r8
0x18000bedf  jz      loc_18000BFDE
0x18000bee5  mov     ecx, 1A44h; cb
0x18000beea  mov     [rsp+48h+arg_8], 1A44h
0x18000bef2  call    cs:__imp_CoTaskMemAlloc
0x18000bef9  nop     dword ptr [rax+rax+00h]
0x18000befe  mov     rdi, rax
0x18000bf01  test    rax, rax
0x18000bf04  jnz     short loc_18000BF21
0x18000bf06  mov     ecx, 8; dwErrCode
0x18000bf0b  call    cs:__imp_SetLastError
0x18000bf12  nop     dword ptr [rax+rax+00h]
0x18000bf17  mov     ebx, 80070008h
0x18000bf1c  jmp     loc_18000BFE3
0x18000bf21  mov     eax, [rsp+48h+arg_8]
0x18000bf25  lea     r9, [rsp+48h+arg_8]; LPDWORD
0x18000bf2a  mov     [rsp+48h+var_20], 0; LPDWORD
0x18000bf33  mov     r8, rdi; struct tagRASENTRYW *
0x18000bf36  mov     rdx, rbp; LPCWSTR
0x18000bf39  mov     [rdi], eax
0x18000bf3b  mov     rcx, r14; LPCWSTR
0x18000bf3e  mov     [rsp+48h+var_28], 0; LPBYTE
0x18000bf47  call    cs:__imp_RasGetEntryPropertiesW
0x18000bf4e  nop     dword ptr [rax+rax+00h]
0x18000bf53  mov     ebx, eax
0x18000bf55  cmp     eax, 25Bh
0x18000bf5a  jnz     short loc_18000BFB7
0x18000bf5c  mov     rcx, rdi; pv
0x18000bf5f  call    cs:__imp_CoTaskMemFree
0x18000bf66  nop     dword ptr [rax+rax+00h]
0x18000bf6b  mov     ecx, [rsp+48h+arg_8]; cb
0x18000bf6f  call    cs:__imp_CoTaskMemAlloc
0x18000bf76  nop     dword ptr [rax+rax+00h]
0x18000bf7b  mov     rdi, rax
0x18000bf7e  test    rax, rax
0x18000bf81  jz      short loc_18000BF06
0x18000bf83  mov     [rsp+48h+var_20], 0; LPDWORD
0x18000bf8c  lea     r9, [rsp+48h+arg_8]; LPDWORD
0x18000bf91  mov     r8, rax; struct tagRASENTRYW *
0x18000bf94  mov     [rsp+48h+var_28], 0; LPBYTE
0x18000bf9d  mov     rdx, rbp; LPCWSTR
0x18000bfa0  mov     dword ptr [rax], 1A44h
0x18000bfa6  mov     rcx, r14; LPCWSTR
0x18000bfa9  call    cs:__imp_RasGetEntryPropertiesW
0x18000bfb0  nop     dword ptr [rax+rax+00h]
0x18000bfb5  mov     ebx, eax
0x18000bfb7  test    ebx, ebx
0x18000bfb9  jnz     short loc_18000BFC0
0x18000bfbb  mov     [rsi], rdi
0x18000bfbe  jmp     short loc_18000BFE3
0x18000bfc0  mov     rcx, rdi; pv
0x18000bfc3  call    cs:__imp_CoTaskMemFree
0x18000bfca  nop     dword ptr [rax+rax+00h]
0x18000bfcf  test    ebx, ebx
0x18000bfd1  jle     short loc_18000BFE3
0x18000bfd3  movzx   ebx, bx
0x18000bfd6  or      ebx, 80070000h
0x18000bfdc  jmp     short loc_18000BFE3
0x18000bfde  mov     ebx, 80070057h
0x18000bfe3  mov     rbp, [rsp+48h+arg_10]
0x18000bfe8  mov     eax, ebx
0x18000bfea  mov     rbx, [rsp+48h+arg_0]
0x18000bfef  add     rsp, 30h
0x18000bff3  pop     r14
0x18000bff5  pop     rdi
0x18000bff6  pop     rsi
0x18000bff7  retn
```
