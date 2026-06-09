# SxRegDeleteKey(HKEY__ *,ushort const *)

- ea: `0x180029728`
- end: `0x1800297d3`
- name: `?SxRegDeleteKey@@YAJPEAUHKEY__@@PEBG@Z`
- size: `171`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180017f60`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180029728`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180029793`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180029793`

## string_xrefs

- `0x180029740`: `SxRegDeleteKey`

## pseudocode

```c
__int64 __fastcall SxRegDeleteKey(HKEY hKey, LPCWSTR lpSubKey)
{
  __int16 v4; // ax
  signed int v5; // ebx
  LSTATUS v6; // eax
  int v8; // [rsp+20h] [rbp-40h] BYREF
  __int16 v9; // [rsp+24h] [rbp-3Ch]
  __int16 v10; // [rsp+26h] [rbp-3Ah]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v8, "SxRegDeleteKey", 568, 2);
  v4 = 570;
  if ( hKey && (v9 = 570, v4 = 571, lpSubKey) )
  {
    v8 = 0;
    v9 = 571;
    v6 = RegDeleteTreeW(hKey, lpSubKey);
    v5 = v6;
    if ( v6 > 0 )
      v5 = (unsigned __int16)v6 | 0x80070000;
    v8 = v5;
    v4 = 573;
    if ( v5 >= 0 )
    {
      v9 = 573;
      goto LABEL_9;
    }
  }
  else
  {
    v5 = -2147024809;
    v8 = -2147024809;
  }
  v10 = v4;
LABEL_9:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v8);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180029728  mov     [rsp-8+arg_0], rbx
0x18002972d  mov     [rsp-8+arg_8], rdi
0x180029732  push    rbp
0x180029733  mov     rbp, rsp
0x180029736  sub     rsp, 60h
0x18002973a  mov     rbx, rdx
0x18002973d  mov     rdi, rcx
0x180029740  lea     rdx, aSxregdeletekey; "SxRegDeleteKey"
0x180029747  mov     r9d, 2; unsigned __int16
0x18002974d  lea     rcx, [rbp+var_40]; this
0x180029751  mov     r8d, 238h; unsigned __int16
0x180029757  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002975c  mov     eax, 23Ah
0x180029761  test    rdi, rdi
0x180029764  jnz     short loc_180029774
0x180029766  mov     ebx, 80070057h
0x18002976b  mov     [rbp+var_40], ebx
0x18002976e  mov     [rbp+var_3A], ax
0x180029772  jmp     short loc_1800297B8
0x180029774  mov     [rbp+var_3C], ax
0x180029778  mov     eax, 23Bh
0x18002977d  test    rbx, rbx
0x180029780  jz      short loc_180029766
0x180029782  mov     rdx, rbx; lpSubKey
0x180029785  mov     [rbp+var_40], 0
0x18002978c  mov     rcx, rdi; hKey
0x18002978f  mov     [rbp+var_3C], ax
0x180029793  call    cs:__imp_RegDeleteTreeW
0x180029799  mov     ebx, eax
0x18002979b  test    eax, eax
0x18002979d  jle     short loc_1800297A8
0x18002979f  movzx   ebx, ax
0x1800297a2  or      ebx, 80070000h
0x1800297a8  mov     [rbp+var_40], ebx
0x1800297ab  mov     eax, 23Dh
0x1800297b0  test    ebx, ebx
0x1800297b2  js      short loc_18002976E
0x1800297b4  mov     [rbp+var_3C], ax
0x1800297b8  lea     rcx, [rbp+var_40]; this
0x1800297bc  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800297c1  mov     rdi, [rsp+60h+arg_8]
0x1800297c6  mov     eax, ebx
0x1800297c8  mov     rbx, [rsp+60h+arg_0]
0x1800297cd  add     rsp, 60h
0x1800297d1  pop     rbp
0x1800297d2  retn
```
