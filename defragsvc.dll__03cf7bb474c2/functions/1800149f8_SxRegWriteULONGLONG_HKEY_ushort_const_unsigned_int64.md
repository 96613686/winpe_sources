# SxRegWriteULONGLONG(HKEY__ *,ushort const *,unsigned __int64)

- ea: `0x1800149f8`
- end: `0x180014ac6`
- name: `?SxRegWriteULONGLONG@@YAJPEAUHKEY__@@PEBG_K@Z`
- size: `206`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800158a4`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x1800149f8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180014a9d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180014a9d`

## string_xrefs

- `0x180014a15`: `SxRegWriteULONGLONG`

## pseudocode

```c
__int64 __fastcall SxRegWriteULONGLONG(HKEY hKey, LPCWSTR lpValueName, __int64 a3)
{
  __int16 v5; // ax
  signed int v6; // ebx
  LSTATUS v8; // eax
  int v9; // [rsp+30h] [rbp-40h] BYREF
  __int16 v10; // [rsp+34h] [rbp-3Ch]
  __int16 v11; // [rsp+36h] [rbp-3Ah]
  __int64 Data; // [rsp+90h] [rbp+20h] BYREF

  Data = a3;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v9, "SxRegWriteULONGLONG", 458, 2);
  v5 = 460;
  if ( hKey && (v10 = 460, v5 = 461, lpValueName) )
  {
    v10 = 461;
    v9 = 0;
    v8 = RegSetValueExW(hKey, lpValueName, 0, 0xBu, (const BYTE *)&Data, 8u);
    v6 = v8;
    if ( v8 > 0 )
      v6 = (unsigned __int16)v8 | 0x80070000;
    v9 = v6;
    v5 = 463;
    if ( v6 >= 0 )
    {
      v10 = 463;
      goto LABEL_4;
    }
  }
  else
  {
    v6 = -2147024809;
    v9 = -2147024809;
  }
  v11 = v5;
LABEL_4:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v9);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800149f8  mov     [rsp-8+arg_0], rbx
0x1800149fd  mov     [rsp-8+arg_8], rdi
0x180014a02  mov     [rsp-8+Data], r8
0x180014a07  push    rbp
0x180014a08  mov     rbp, rsp
0x180014a0b  sub     rsp, 70h
0x180014a0f  mov     rbx, rdx
0x180014a12  mov     rdi, rcx
0x180014a15  lea     rdx, aSxregwriteulon; "SxRegWriteULONGLONG"
0x180014a1c  mov     r9d, 2; unsigned __int16
0x180014a22  lea     rcx, [rbp+var_40]; this
0x180014a26  mov     r8d, 1CAh; unsigned __int16
0x180014a2c  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180014a31  mov     eax, 1CCh
0x180014a36  test    rdi, rdi
0x180014a39  jnz     short loc_180014A64
0x180014a3b  mov     ebx, 80070057h
0x180014a40  mov     [rbp+var_40], ebx
0x180014a43  mov     [rbp+var_3A], ax
0x180014a47  lea     rcx, [rbp+var_40]; this
0x180014a4b  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180014a50  lea     r11, [rsp+70h+var_s0]
0x180014a55  mov     eax, ebx
0x180014a57  mov     rbx, [r11+10h]
0x180014a5b  mov     rdi, [r11+18h]
0x180014a5f  mov     rsp, r11
0x180014a62  pop     rbp
0x180014a63  retn
0x180014a64  mov     [rbp+var_3C], ax
0x180014a68  mov     eax, 1CDh
0x180014a6d  test    rbx, rbx
0x180014a70  jz      short loc_180014A3B
0x180014a72  mov     [rbp+var_3C], ax
0x180014a76  mov     r9d, 0Bh; dwType
0x180014a7c  lea     rax, [rbp+Data]
0x180014a80  mov     [rsp+70h+cbData], 8; cbData
0x180014a88  xor     r8d, r8d; Reserved
0x180014a8b  mov     [rsp+70h+lpData], rax; lpData
0x180014a90  mov     rdx, rbx; lpValueName
0x180014a93  mov     [rbp+var_40], 0
0x180014a9a  mov     rcx, rdi; hKey
0x180014a9d  call    cs:__imp_RegSetValueExW
0x180014aa3  mov     ebx, eax
0x180014aa5  test    eax, eax
0x180014aa7  jg      short loc_180014ABB
0x180014aa9  mov     [rbp+var_40], ebx
0x180014aac  mov     eax, 1CFh
0x180014ab1  test    ebx, ebx
0x180014ab3  js      short loc_180014A43
0x180014ab5  mov     [rbp+var_3C], ax
0x180014ab9  jmp     short loc_180014A47
0x180014abb  movzx   ebx, ax
0x180014abe  or      ebx, 80070000h
0x180014ac4  jmp     short loc_180014AA9
```
