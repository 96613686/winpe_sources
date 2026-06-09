# _RequireMutualAuth

- ea: `0x180012820`
- end: `0x1800128a2`
- name: `_RequireMutualAuth`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012604`

## callees

- `0x18000d650`
- `0x180012820`

## string_xrefs

- `0x18001286b`: `Security\RequireMutualAuthRpc`

## pseudocode

```c
__int64 RequireMutualAuth()
{
  __int64 result; // rax
  unsigned int v1; // [rsp+40h] [rbp+8h] BYREF
  _BYTE v2[8]; // [rsp+48h] [rbp+10h] BYREF
  unsigned int v3; // [rsp+50h] [rbp+18h] BYREF
  unsigned int v4; // [rsp+58h] [rbp+20h] BYREF

  if ( g_fRequireMutualAuthInitialized )
    return g_dwRequireMutualAuth;
  v1 = 0;
  v4 = 4;
  v3 = 4;
  wcscpy((wchar_t *)v2, L"\x01");
  if ( GetFalconKeyValue(L"Security\\RequireMutualAuthRpc", &v4, &v1, &v3, (const wchar_t *)v2) )
  {
    g_dwRequireMutualAuth = 1;
    result = 1;
  }
  else
  {
    result = v1;
    g_dwRequireMutualAuth = v1;
  }
  g_fRequireMutualAuthInitialized = 1;
  return result;
}

```

## disassembly

```asm
0x180012820  sub     rsp, 38h
0x180012824  cmp     cs:?g_fRequireMutualAuthInitialized@@3_NA, 0; bool g_fRequireMutualAuthInitialized
0x18001282b  jz      short loc_180012835
0x18001282d  mov     eax, cs:?g_dwRequireMutualAuth@@3KA; ulong g_dwRequireMutualAuth
0x180012833  jmp     short loc_18001289D
0x180012835  mov     eax, 4
0x18001283a  mov     [rsp+38h+arg_0], 0
0x180012842  mov     [rsp+38h+arg_18], eax
0x180012846  lea     r9, [rsp+38h+arg_10]; unsigned int *
0x18001284b  mov     [rsp+38h+arg_10], eax
0x18001284f  lea     r8, [rsp+38h+arg_0]; void *
0x180012854  lea     rax, [rsp+38h+arg_8]
0x180012859  mov     dword ptr [rsp+38h+arg_8], 1
0x180012861  lea     rdx, [rsp+38h+arg_18]; unsigned int *
0x180012866  mov     [rsp+38h+var_18], rax; wchar_t *
0x18001286b  lea     rcx, aSecurityRequir; "Security\\RequireMutualAuthRpc"
0x180012872  call    ?GetFalconKeyValue@@YAJPEB_WPEAKPEAX10@Z; GetFalconKeyValue(wchar_t const *,ulong *,void *,ulong *,wchar_t const *)
0x180012877  test    eax, eax
0x180012879  jnz     short loc_180012887
0x18001287b  mov     eax, [rsp+38h+arg_0]
0x18001287f  mov     cs:?g_dwRequireMutualAuth@@3KA, eax; ulong g_dwRequireMutualAuth
0x180012885  jmp     short loc_180012896
0x180012887  mov     cs:?g_dwRequireMutualAuth@@3KA, 1; ulong g_dwRequireMutualAuth
0x180012891  mov     eax, 1
0x180012896  mov     cs:?g_fRequireMutualAuthInitialized@@3_NA, 1; bool g_fRequireMutualAuthInitialized
0x18001289d  add     rsp, 38h
0x1800128a1  retn
```
