# UtilLoadStringWithAlloc(uint,ushort * *,uint)

- ea: `0x1800107f0`
- end: `0x1800108a1`
- name: `?UtilLoadStringWithAlloc@@YAJIPEAPEAGI@Z`
- size: `177`
- prototype: `__int64 __fastcall(UINT uID, unsigned __int16 **, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010684`

## callees

- `0x1800107f0`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18001083d`
- `KERNEL32!GetModuleHandleW` at `0x18001083d`
- `KERNEL32!GetLastError` at `0x180010864`
- `KERNEL32!GetLastError` at `0x180010864`
- `USER32!LoadStringW` at `0x180010854`
- `USER32!LoadStringW` at `0x180010854`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010882`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010882`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010811`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010811`

## pseudocode

```c
__int64 __fastcall UtilLoadStringWithAlloc(UINT uID, unsigned __int16 **a2, unsigned int a3)
{
  unsigned __int16 *v6; // rdi
  HMODULE ModuleHandleW; // rax
  signed int LastError; // eax
  unsigned int v10; // ebx

  if ( !a2 )
  {
    if ( !a3 )
      goto LABEL_3;
    return 2147942487LL;
  }
  if ( a3 > 0xFFFF )
    return 2147942487LL;
LABEL_3:
  v6 = (unsigned __int16 *)CoTaskMemAlloc(2LL * a3);
  if ( !v6 )
    return 2147942414LL;
  ModuleHandleW = GetModuleHandleW(0);
  if ( LoadStringW(ModuleHandleW, uID, v6, a3) )
  {
    *a2 = v6;
    return 0;
  }
  else
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    CoTaskMemFree(v6);
    return v10;
  }
}

```

## disassembly

```asm
0x1800107f0  push    rbx
0x1800107f2  push    rbp
0x1800107f3  push    rsi
0x1800107f4  push    rdi
0x1800107f5  sub     rsp, 28h
0x1800107f9  mov     ebx, r8d
0x1800107fc  mov     rsi, rdx
0x1800107ff  mov     ebp, ecx
0x180010801  test    rdx, rdx
0x180010804  jnz     short loc_18001082C
0x180010806  test    r8d, r8d
0x180010809  jnz     short loc_180010834
0x18001080b  mov     rcx, rbx
0x18001080e  add     rcx, rcx; cb
0x180010811  call    cs:__imp_CoTaskMemAlloc
0x180010818  nop     dword ptr [rax+rax+00h]
0x18001081d  mov     rdi, rax
0x180010820  test    rax, rax
0x180010823  jnz     short loc_18001083B
0x180010825  mov     eax, 8007000Eh
0x18001082a  jmp     short loc_180010897
0x18001082c  cmp     ebx, 0FFFFh
0x180010832  jbe     short loc_18001080B
0x180010834  mov     eax, 80070057h
0x180010839  jmp     short loc_180010897
0x18001083b  xor     ecx, ecx; lpModuleName
0x18001083d  call    cs:__imp_GetModuleHandleW
0x180010844  nop     dword ptr [rax+rax+00h]
0x180010849  mov     r9d, ebx; cchBufferMax
0x18001084c  mov     r8, rdi; lpBuffer
0x18001084f  mov     rcx, rax; hInstance
0x180010852  mov     edx, ebp; uID
0x180010854  call    cs:__imp_LoadStringW
0x18001085b  nop     dword ptr [rax+rax+00h]
0x180010860  test    eax, eax
0x180010862  jnz     short loc_180010892
0x180010864  call    cs:__imp_GetLastError
0x18001086b  nop     dword ptr [rax+rax+00h]
0x180010870  mov     ebx, eax
0x180010872  test    eax, eax
0x180010874  jle     short loc_18001087F
0x180010876  movzx   ebx, ax
0x180010879  or      ebx, 80070000h
0x18001087f  mov     rcx, rdi; pv
0x180010882  call    cs:__imp_CoTaskMemFree
0x180010889  nop     dword ptr [rax+rax+00h]
0x18001088e  mov     eax, ebx
0x180010890  jmp     short loc_180010897
0x180010892  mov     [rsi], rdi
0x180010895  xor     eax, eax
0x180010897  add     rsp, 28h
0x18001089b  pop     rdi
0x18001089c  pop     rsi
0x18001089d  pop     rbp
0x18001089e  pop     rbx
0x18001089f  retn
```
