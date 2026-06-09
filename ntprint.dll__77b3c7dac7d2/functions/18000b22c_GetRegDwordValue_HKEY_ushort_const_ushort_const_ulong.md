# GetRegDwordValue(HKEY__ *,ushort const *,ushort const *,ulong *)

- ea: `0x18000b22c`
- end: `0x18000b30e`
- name: `?GetRegDwordValue@@YAJPEAUHKEY__@@PEBG1PEAK@Z`
- size: `226`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000c2a4`
- `0x180011c20`

## callees

- `0x18000b22c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b2f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b2f6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b2c0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b2c0`
- `ADVAPI32!RegOpenKeyW` at `0x18000b27e`
- `ADVAPI32!RegOpenKeyW` at `0x18000b27e`

## pseudocode

```c
__int64 __fastcall GetRegDwordValue(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3, unsigned int *a4)
{
  LSTATUS v6; // eax
  signed int v7; // ebx
  LSTATUS v8; // eax
  BYTE Data[4]; // [rsp+30h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-14h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-10h] BYREF
  DWORD Type; // [rsp+70h] [rbp+28h] BYREF
  int v14; // [rsp+74h] [rbp+2Ch]

  v14 = HIDWORD(a1);
  phkResult = 0;
  *(_DWORD *)Data = 0;
  Type = 0;
  if ( a2 && a3 && a4 )
  {
    v6 = RegOpenKeyW(HKEY_LOCAL_MACHINE, a2, &phkResult);
    v7 = v6;
    if ( !v6 )
      goto LABEL_8;
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    if ( v7 >= 0 )
    {
LABEL_8:
      cbData = 4;
      v8 = RegQueryValueExW(phkResult, a3, 0, &Type, Data, &cbData);
      v7 = v8;
      if ( !v8 )
        goto LABEL_12;
      if ( v8 > 0 )
        v7 = (unsigned __int16)v8 | 0x80070000;
      if ( v7 >= 0 )
      {
LABEL_12:
        if ( Type == 4 )
          *a4 = *(_DWORD *)Data;
        else
          v7 = -2147418113;
      }
    }
    if ( phkResult )
      RegCloseKey(phkResult);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000b22c  mov     qword ptr [rsp-20h+Type], rcx
0x18000b231  push    rbp
0x18000b232  push    rbx
0x18000b233  push    rsi
0x18000b234  push    rdi
0x18000b235  mov     rbp, rsp
0x18000b238  sub     rsp, 48h
0x18000b23c  mov     [rbp+phkResult], 0
0x18000b244  mov     rdi, r9
0x18000b247  mov     dword ptr [rbp+Data], 0
0x18000b24e  mov     rsi, r8
0x18000b251  mov     [rbp+Type], 0
0x18000b258  test    rdx, rdx
0x18000b25b  jz      loc_18000B2FE
0x18000b261  test    r8, r8
0x18000b264  jz      loc_18000B2FE
0x18000b26a  test    r9, r9
0x18000b26d  jz      loc_18000B2FE
0x18000b273  lea     r8, [rbp+phkResult]; phkResult
0x18000b277  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b27e  call    cs:__imp_RegOpenKeyW
0x18000b284  mov     ebx, eax
0x18000b286  test    eax, eax
0x18000b288  jz      short loc_18000B299
0x18000b28a  jle     short loc_18000B295
0x18000b28c  movzx   ebx, ax
0x18000b28f  or      ebx, 80070000h
0x18000b295  test    ebx, ebx
0x18000b297  js      short loc_18000B2ED
0x18000b299  mov     rcx, [rbp+phkResult]; hKey
0x18000b29d  lea     rax, [rbp+cbData]
0x18000b2a1  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18000b2a6  lea     r9, [rbp+Type]; lpType
0x18000b2aa  lea     rax, [rbp+Data]
0x18000b2ae  mov     [rbp+cbData], 4
0x18000b2b5  xor     r8d, r8d; lpReserved
0x18000b2b8  mov     [rsp+48h+lpData], rax; lpData
0x18000b2bd  mov     rdx, rsi; lpValueName
0x18000b2c0  call    cs:__imp_RegQueryValueExW
0x18000b2c6  mov     ebx, eax
0x18000b2c8  test    eax, eax
0x18000b2ca  jz      short loc_18000B2DB
0x18000b2cc  jle     short loc_18000B2D7
0x18000b2ce  movzx   ebx, ax
0x18000b2d1  or      ebx, 80070000h
0x18000b2d7  test    ebx, ebx
0x18000b2d9  js      short loc_18000B2ED
0x18000b2db  cmp     [rbp+Type], 4
0x18000b2df  jnz     short loc_18000B2E8
0x18000b2e1  mov     eax, dword ptr [rbp+Data]
0x18000b2e4  mov     [rdi], eax
0x18000b2e6  jmp     short loc_18000B2ED
0x18000b2e8  mov     ebx, 8000FFFFh
0x18000b2ed  mov     rcx, [rbp+phkResult]; hKey
0x18000b2f1  test    rcx, rcx
0x18000b2f4  jz      short loc_18000B303
0x18000b2f6  call    cs:__imp_RegCloseKey
0x18000b2fc  jmp     short loc_18000B303
0x18000b2fe  mov     ebx, 80070057h
0x18000b303  mov     eax, ebx
0x18000b305  add     rsp, 48h
0x18000b309  pop     rdi
0x18000b30a  pop     rsi
0x18000b30b  pop     rbx
0x18000b30c  pop     rbp
0x18000b30d  retn
```
