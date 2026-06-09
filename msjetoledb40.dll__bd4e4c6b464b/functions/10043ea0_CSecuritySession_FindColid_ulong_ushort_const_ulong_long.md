# CSecuritySession::FindColid(ulong,ushort const *,ulong &,long &)

- ea: `0x10043ea0`
- end: `0x10043f15`
- name: `?FindColid@CSecuritySession@@QAEJKPBGAAKAAJ@Z`
- size: `117`
- prototype: `int __thiscall(CSecuritySession *__hidden this, unsigned int, const unsigned __int16 *, unsigned int *, int *)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x100413c0`
- `0x10041890`
- `0x10041f50`
- `0x10043f20`

## callees

- `0x10043ea0`
- `0x1004d420`

## import_xrefs

- `msjet40!__imp__JetGetTableColumnInfo@24` at `0x10043ed9`
- `msjet40!__imp__JetGetTableColumnInfo@24` at `0x10043ed9`

## pseudocode

```c
int __thiscall CSecuritySession::FindColid(
        CSecuritySession *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        unsigned int *a4,
        int *a5)
{
  int TableColumnInfo; // eax
  int result; // eax
  int v7; // [esp-18h] [ebp-3Ch]
  _DWORD v8[6]; // [esp+8h] [ebp-1Ch] BYREF

  *a4 = -1;
  v7 = *((_DWORD *)this + 1);
  v8[0] = 24;
  TableColumnInfo = JetGetTableColumnInfo(v7, a2, a3, v8, 24, 0);
  *a5 = TableColumnInfo;
  if ( TableColumnInfo < 0 )
    return -2147467259;
  result = 0;
  *a4 = v8[1];
  return result;
}

```

## disassembly

```asm
0x10043ea0  mov     edi, edi
0x10043ea2  push    ebp
0x10043ea3  mov     ebp, esp
0x10043ea5  sub     esp, 1Ch
0x10043ea8  mov     eax, ___security_cookie
0x10043ead  xor     eax, ebp
0x10043eaf  mov     [ebp+var_4], eax
0x10043eb2  mov     eax, [ebp+arg_4]
0x10043eb5  lea     edx, [ebp+var_1C]
0x10043eb8  push    esi
0x10043eb9  mov     esi, [ebp+arg_C]
0x10043ebc  push    edi
0x10043ebd  mov     edi, [ebp+arg_8]
0x10043ec0  push    0
0x10043ec2  push    18h
0x10043ec4  push    edx
0x10043ec5  push    eax
0x10043ec6  push    [ebp+arg_0]
0x10043ec9  mov     dword ptr [edi], 0FFFFFFFFh
0x10043ecf  push    dword ptr [ecx+4]
0x10043ed2  mov     [ebp+var_1C], 18h
0x10043ed9  call    ds:__imp__JetGetTableColumnInfo@24; JetGetTableColumnInfo(x,x,x,x,x,x)
0x10043edf  mov     [esi], eax
0x10043ee1  test    eax, eax
0x10043ee3  jns     short loc_10043EFC
0x10043ee5  pop     edi
0x10043ee6  mov     eax, 80004005h
0x10043eeb  pop     esi
0x10043eec  mov     ecx, [ebp+var_4]
0x10043eef  xor     ecx, ebp; StackCookie
0x10043ef1  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10043ef6  mov     esp, ebp
0x10043ef8  pop     ebp
0x10043ef9  retn    10h
0x10043efc  mov     ecx, [ebp+var_18]
0x10043eff  xor     eax, eax
0x10043f01  mov     [edi], ecx
0x10043f03  mov     ecx, [ebp+var_4]
0x10043f06  pop     edi
0x10043f07  xor     ecx, ebp; StackCookie
0x10043f09  pop     esi
0x10043f0a  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10043f0f  mov     esp, ebp
0x10043f11  pop     ebp
0x10043f12  retn    10h
```
