# SxRegWriteDWORD(HKEY__ *,ushort const *,ulong)

- ea: `0x180015728`
- end: `0x1800157f3`
- name: `?SxRegWriteDWORD@@YAJPEAUHKEY__@@PEBGK@Z`
- size: `203`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800158a4`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180015728`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800157ca`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800157ca`

## string_xrefs

- `0x180015745`: `SxRegWriteDWORD`

## pseudocode

```c
__int64 __fastcall SxRegWriteDWORD(HKEY hKey, LPCWSTR lpValueName, int a3)
{
  __int16 v5; // ax
  signed int v6; // ebx
  LSTATUS v8; // eax
  int v9; // [rsp+30h] [rbp-40h] BYREF
  __int16 v10; // [rsp+34h] [rbp-3Ch]
  __int16 v11; // [rsp+36h] [rbp-3Ah]
  int Data; // [rsp+90h] [rbp+20h] BYREF

  Data = a3;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v9, "SxRegWriteDWORD", 438, 2);
  v5 = 440;
  if ( hKey && (v10 = 440, v5 = 441, lpValueName) )
  {
    v10 = 441;
    v9 = 0;
    v8 = RegSetValueExW(hKey, lpValueName, 0, 4u, (const BYTE *)&Data, 4u);
    v6 = v8;
    if ( v8 > 0 )
      v6 = (unsigned __int16)v8 | 0x80070000;
    v9 = v6;
    v5 = 443;
    if ( v6 >= 0 )
    {
      v10 = 443;
      goto LABEL_5;
    }
  }
  else
  {
    v6 = -2147024809;
    v9 = -2147024809;
  }
  v11 = v5;
LABEL_5:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v9);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180015728  mov     [rsp-8+arg_0], rbx
0x18001572d  mov     [rsp-8+arg_8], rdi
0x180015732  mov     [rsp-8+Data], r8d
0x180015737  push    rbp
0x180015738  mov     rbp, rsp
0x18001573b  sub     rsp, 70h
0x18001573f  mov     rbx, rdx
0x180015742  mov     rdi, rcx
0x180015745  lea     rdx, aSxregwritedwor; "SxRegWriteDWORD"
0x18001574c  mov     r9d, 2; unsigned __int16
0x180015752  lea     rcx, [rbp+var_40]; this
0x180015756  mov     r8d, 1B6h; unsigned __int16
0x18001575c  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180015761  mov     eax, 1B8h
0x180015766  test    rdi, rdi
0x180015769  jz      short loc_180015779
0x18001576b  mov     [rbp+var_3C], ax
0x18001576f  mov     eax, 1B9h
0x180015774  test    rbx, rbx
0x180015777  jnz     short loc_1800157A2
0x180015779  mov     ebx, 80070057h
0x18001577e  mov     [rbp+var_40], ebx
0x180015781  mov     [rbp+var_3A], ax
0x180015785  lea     rcx, [rbp+var_40]; this
0x180015789  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001578e  lea     r11, [rsp+70h+var_s0]
0x180015793  mov     eax, ebx
0x180015795  mov     rbx, [r11+10h]
0x180015799  mov     rdi, [r11+18h]
0x18001579d  mov     rsp, r11
0x1800157a0  pop     rbp
0x1800157a1  retn
0x1800157a2  mov     [rbp+var_3C], ax
0x1800157a6  mov     r9d, 4; dwType
0x1800157ac  lea     rax, [rbp+Data]
0x1800157b0  mov     [rsp+70h+cbData], r9d; cbData
0x1800157b5  xor     r8d, r8d; Reserved
0x1800157b8  mov     [rsp+70h+lpData], rax; lpData
0x1800157bd  mov     rdx, rbx; lpValueName
0x1800157c0  mov     [rbp+var_40], 0
0x1800157c7  mov     rcx, rdi; hKey
0x1800157ca  call    cs:__imp_RegSetValueExW
0x1800157d0  mov     ebx, eax
0x1800157d2  test    eax, eax
0x1800157d4  jg      short loc_1800157E8
0x1800157d6  mov     [rbp+var_40], ebx
0x1800157d9  mov     eax, 1BBh
0x1800157de  test    ebx, ebx
0x1800157e0  js      short loc_180015781
0x1800157e2  mov     [rbp+var_3C], ax
0x1800157e6  jmp     short loc_180015785
0x1800157e8  movzx   ebx, ax
0x1800157eb  or      ebx, 80070000h
0x1800157f1  jmp     short loc_1800157D6
```
