# InitializeCOM(int *)

- ea: `0x180026c60`
- end: `0x180026ce2`
- name: `?InitializeCOM@@YAJPEAH@Z`
- size: `130`
- prototype: `HRESULT __fastcall(int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002477c`
- `0x180026914`

## callees

- `0x180026c60`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x180026cca`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x180026cca`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180026c73`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180026c73`

## pseudocode

```c
HRESULT __fastcall InitializeCOM(int *a1)
{
  HRESULT result; // eax
  HRESULT v3; // eax
  int v4; // ecx

  *a1 = 0;
  result = CoInitializeEx(0, 0);
  switch ( result )
  {
    case 0:
      *a1 = 1;
      return result;
    case 1:
      *a1 = 1;
      break;
    case -2147417850:
      break;
    default:
      return result;
  }
  v3 = CoInitializeSecurity(0, -1, 0, 0, 0, 3u, 0, 0, 0);
  v4 = 0;
  if ( v3 != -2147417831 )
    return v3;
  return v4;
}

```

## disassembly

```asm
0x180026c60  push    rbx
0x180026c62  sub     rsp, 50h
0x180026c66  mov     rbx, rcx
0x180026c69  mov     dword ptr [rcx], 0
0x180026c6f  xor     ecx, ecx; pvReserved
0x180026c71  xor     edx, edx; dwCoInit
0x180026c73  call    cs:__imp_CoInitializeEx
0x180026c79  test    eax, eax
0x180026c7b  jnz     short loc_180026C85
0x180026c7d  mov     dword ptr [rbx], 1
0x180026c83  jmp     short loc_180026CDC
0x180026c85  cmp     eax, 1
0x180026c88  jnz     short loc_180026C8E
0x180026c8a  mov     [rbx], eax
0x180026c8c  jmp     short loc_180026C95
0x180026c8e  cmp     eax, 80010106h
0x180026c93  jnz     short loc_180026CDC
0x180026c95  mov     [rsp+58h+pReserved3], 0; pReserved3
0x180026c9e  xor     r9d, r9d; pReserved1
0x180026ca1  mov     [rsp+58h+dwCapabilities], 0; dwCapabilities
0x180026ca9  xor     r8d, r8d; asAuthSvc
0x180026cac  mov     [rsp+58h+pAuthList], 0; pAuthList
0x180026cb5  or      edx, 0FFFFFFFFh; cAuthSvc
0x180026cb8  mov     [rsp+58h+dwImpLevel], 3; dwImpLevel
0x180026cc0  xor     ecx, ecx; pSecDesc
0x180026cc2  mov     [rsp+58h+dwAuthnLevel], 0; dwAuthnLevel
0x180026cca  call    cs:__imp_CoInitializeSecurity
0x180026cd0  xor     ecx, ecx
0x180026cd2  cmp     eax, 80010119h
0x180026cd7  cmovnz  ecx, eax
0x180026cda  mov     eax, ecx
0x180026cdc  add     rsp, 50h
0x180026ce0  pop     rbx
0x180026ce1  retn
```
