# UpdatePreFetchParaFromRegistry

- ea: `0x18000c370`
- end: `0x18000c3e5`
- name: `UpdatePreFetchParaFromRegistry`
- size: `117`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *, _DWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x18000c46c`
- `0x180010f90`

## callees

- `0x18000c370`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c3d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c3d1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c3aa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c3aa`

## pseudocode

```c
__int64 __fastcall UpdatePreFetchParaFromRegistry(HKEY a1, const WCHAR *a2, _DWORD *a3)
{
  LSTATUS v4; // eax
  DWORD v5; // ecx
  __int64 result; // rax
  DWORD v7; // [rsp+30h] [rbp-18h] BYREF
  BYTE v8[20]; // [rsp+34h] [rbp-14h] BYREF
  DWORD v9; // [rsp+68h] [rbp+20h] BYREF

  v9 = 0;
  *(_DWORD *)v8 = 0;
  v7 = 4;
  v4 = RegQueryValueExW(a1, a2, 0, &v9, v8, &v7);
  if ( v4 )
  {
    v5 = v4;
  }
  else
  {
    if ( v9 == 4 && v7 == 4 )
    {
      result = *(unsigned int *)v8;
      goto LABEL_8;
    }
    v5 = -2146885629;
  }
  SetLastError(v5);
  result = 0;
LABEL_8:
  if ( (_DWORD)result )
    *a3 = result;
  return result;
}

```

## disassembly

```asm
0x18000c370  mov     r11, rsp
0x18000c373  push    rbx
0x18000c374  sub     rsp, 40h
0x18000c378  lea     rax, [r11-18h]
0x18000c37c  mov     [rsp+48h+arg_18], 0
0x18000c384  mov     [r11-20h], rax
0x18000c388  lea     r9, [r11+20h]; lpType
0x18000c38c  lea     rax, [r11-14h]
0x18000c390  mov     dword ptr [rsp+48h+var_14], 0
0x18000c398  mov     rbx, r8
0x18000c39b  mov     [r11-28h], rax
0x18000c39f  xor     r8d, r8d; lpReserved
0x18000c3a2  mov     [rsp+48h+var_18], 4
0x18000c3aa  call    cs:__imp_RegQueryValueExW
0x18000c3b0  test    eax, eax
0x18000c3b2  jz      short loc_18000C3B8
0x18000c3b4  mov     ecx, eax
0x18000c3b6  jmp     short loc_18000C3D1
0x18000c3b8  cmp     [rsp+48h+arg_18], 4
0x18000c3bd  jnz     short loc_18000C3CC
0x18000c3bf  cmp     [rsp+48h+var_18], 4
0x18000c3c4  jnz     short loc_18000C3CC
0x18000c3c6  mov     eax, dword ptr [rsp+48h+var_14]
0x18000c3ca  jmp     short loc_18000C3D9
0x18000c3cc  mov     ecx, 80092003h; dwErrCode
0x18000c3d1  call    cs:__imp_SetLastError
0x18000c3d7  xor     eax, eax
0x18000c3d9  test    eax, eax
0x18000c3db  jz      short loc_18000C3DF
0x18000c3dd  mov     [rbx], eax
0x18000c3df  add     rsp, 40h
0x18000c3e3  pop     rbx
0x18000c3e4  retn
```
