# SxRegWriteString(HKEY__ *,ushort const *,ushort const *)

- ea: `0x18004ea08`
- end: `0x18004ead4`
- name: `?SxRegWriteString@@YAJPEAUHKEY__@@PEBG1@Z`
- size: `204`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, BYTE *lpData)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180010c20`
- `0x1800546e8`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18004ea08`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004ea99`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004ea99`

## string_xrefs

- `0x18004ea1f`: `SxRegWriteString`

## pseudocode

```c
__int64 __fastcall SxRegWriteString(HKEY hKey, LPCWSTR lpValueName, BYTE *lpData)
{
  __int16 v6; // ax
  signed int v7; // ebx
  __int64 v8; // rax
  LSTATUS v9; // eax
  int v11; // [rsp+30h] [rbp-40h] BYREF
  __int16 v12; // [rsp+34h] [rbp-3Ch]
  __int16 v13; // [rsp+36h] [rbp-3Ah]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v11, "SxRegWriteString", 478, 2);
  v6 = 480;
  if ( hKey && (v12 = 480, v6 = 481, lpData) )
  {
    v12 = 481;
    v8 = -1;
    v11 = 0;
    do
      ++v8;
    while ( *(_WORD *)&lpData[2 * v8] );
    v9 = RegSetValueExW(hKey, lpValueName, 0, 1u, lpData, 2 * v8 + 2);
    v7 = v9;
    if ( v9 > 0 )
      v7 = (unsigned __int16)v9 | 0x80070000;
    v11 = v7;
    v6 = 483;
    if ( v7 >= 0 )
    {
      v12 = 483;
      goto LABEL_11;
    }
  }
  else
  {
    v7 = -2147024809;
    v11 = -2147024809;
  }
  v13 = v6;
LABEL_11:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v11);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18004ea08  push    rbp
0x18004ea0a  push    rbx
0x18004ea0b  push    rsi
0x18004ea0c  push    rdi
0x18004ea0d  push    r14
0x18004ea0f  mov     rbp, rsp
0x18004ea12  sub     rsp, 70h
0x18004ea16  mov     rbx, r8
0x18004ea19  mov     rsi, rdx
0x18004ea1c  mov     rdi, rcx
0x18004ea1f  lea     rdx, aSxregwritestri; "SxRegWriteString"
0x18004ea26  mov     r8d, 1DEh; unsigned __int16
0x18004ea2c  lea     rcx, [rbp+var_40]; this
0x18004ea30  mov     r9d, 2; unsigned __int16
0x18004ea36  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18004ea3b  xor     r14d, r14d
0x18004ea3e  mov     eax, 1E0h
0x18004ea43  test    rdi, rdi
0x18004ea46  jnz     short loc_18004EA56
0x18004ea48  mov     ebx, 80070057h
0x18004ea4d  mov     [rbp+var_40], ebx
0x18004ea50  mov     [rbp+var_3A], ax
0x18004ea54  jmp     short loc_18004EABE
0x18004ea56  mov     [rbp+var_3C], ax
0x18004ea5a  mov     eax, 1E1h
0x18004ea5f  test    rbx, rbx
0x18004ea62  jz      short loc_18004EA48
0x18004ea64  mov     [rbp+var_3C], ax
0x18004ea68  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004ea6c  mov     [rbp+var_40], r14d
0x18004ea70  inc     rax
0x18004ea73  cmp     [rbx+rax*2], r14w
0x18004ea78  jnz     short loc_18004EA70
0x18004ea7a  lea     eax, ds:2[rax*2]
0x18004ea81  mov     r9d, 1; dwType
0x18004ea87  mov     [rsp+70h+cbData], eax; cbData
0x18004ea8b  xor     r8d, r8d; Reserved
0x18004ea8e  mov     rdx, rsi; lpValueName
0x18004ea91  mov     [rsp+70h+lpData], rbx; lpData
0x18004ea96  mov     rcx, rdi; hKey
0x18004ea99  call    cs:__imp_RegSetValueExW
0x18004ea9f  mov     ebx, eax
0x18004eaa1  test    eax, eax
0x18004eaa3  jle     short loc_18004EAAE
0x18004eaa5  movzx   ebx, ax
0x18004eaa8  or      ebx, 80070000h
0x18004eaae  mov     [rbp+var_40], ebx
0x18004eab1  mov     eax, 1E3h
0x18004eab6  test    ebx, ebx
0x18004eab8  js      short loc_18004EA50
0x18004eaba  mov     [rbp+var_3C], ax
0x18004eabe  lea     rcx, [rbp+var_40]; this
0x18004eac2  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18004eac7  mov     eax, ebx
0x18004eac9  add     rsp, 70h
0x18004eacd  pop     r14
0x18004eacf  pop     rdi
0x18004ead0  pop     rsi
0x18004ead1  pop     rbx
0x18004ead2  pop     rbp
0x18004ead3  retn
```
