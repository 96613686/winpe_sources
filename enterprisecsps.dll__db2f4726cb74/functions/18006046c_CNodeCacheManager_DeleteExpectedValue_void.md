# CNodeCacheManager::DeleteExpectedValue(void)

- ea: `0x18006046c`
- end: `0x18006054d`
- name: `?DeleteExpectedValue@CNodeCacheManager@@QEAAJXZ`
- size: `225`
- prototype: `__int64 __fastcall(CNodeCacheManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180057ca4`

## callees

- `0x18006046c`
- `0x180060f20`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800604b3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800604cf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800604eb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180060507`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800604b3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800604cf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800604eb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180060507`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060538`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060538`

## pseudocode

```c
__int64 __fastcall CNodeCacheManager::DeleteExpectedValue(CNodeCacheManager *this)
{
  const unsigned __int16 *v1; // r9
  const unsigned __int16 *v2; // r8
  const unsigned __int16 *v3; // rdx
  signed int NodeIdKey; // ebx
  LSTATUS v5; // eax
  bool v6; // cc
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  v1 = (const unsigned __int16 *)*((_QWORD *)this + 2);
  v2 = (const unsigned __int16 *)*((_QWORD *)this + 1);
  v3 = *(const unsigned __int16 **)this;
  hKey = 0;
  NodeIdKey = CNodeCacheManager::GetNodeIdKey(this, v3, v2, v1, &hKey, 0);
  if ( NodeIdKey >= 0 )
  {
    v5 = RegDeleteValueW(hKey, L"ExpectedValue");
    v6 = v5 <= 0;
    if ( !v5 )
    {
      v5 = RegDeleteValueW(hKey, L"ExpectedValueType");
      v6 = v5 <= 0;
      if ( !v5 )
      {
        v5 = RegDeleteValueW(hKey, L"ExpectedValueDataType");
        v6 = v5 <= 0;
        if ( !v5 )
        {
          v5 = RegDeleteValueW(hKey, L"ExpectedValueSemanticType");
          if ( (v5 & 0xFFFFFFFD) == 0 )
            goto LABEL_10;
          v6 = v5 <= 0;
        }
      }
    }
    if ( v6 )
      NodeIdKey = v5;
    else
      NodeIdKey = (unsigned __int16)v5 | 0x80070000;
  }
LABEL_10:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)NodeIdKey;
}

```

## disassembly

```asm
0x18006046c  push    rbx
0x18006046e  sub     rsp, 30h
0x180060472  mov     r9, [rcx+10h]; unsigned __int16 *
0x180060476  lea     rax, [rsp+38h+hKey]
0x18006047b  mov     r8, [rcx+8]; unsigned __int16 *
0x18006047f  mov     rdx, [rcx]; unsigned __int16 *
0x180060482  mov     [rsp+38h+var_10], 0; int
0x18006048a  mov     [rsp+38h+var_18], rax; HKEY *
0x18006048f  mov     [rsp+38h+hKey], 0
0x180060498  call    ?GetNodeIdKey@CNodeCacheManager@@AEAAJPEBG00PEAPEAUHKEY__@@H@Z; CNodeCacheManager::GetNodeIdKey(ushort const *,ushort const *,ushort const *,HKEY__ * *,int)
0x18006049d  mov     ebx, eax
0x18006049f  test    eax, eax
0x1800604a1  js      loc_18006052B
0x1800604a7  mov     rcx, [rsp+38h+hKey]; hKey
0x1800604ac  lea     rdx, aExpectedvalue_0; "ExpectedValue"
0x1800604b3  call    cs:__imp_RegDeleteValueW
0x1800604ba  nop     dword ptr [rax+rax+00h]
0x1800604bf  test    eax, eax
0x1800604c1  jnz     short loc_18006051C
0x1800604c3  mov     rcx, [rsp+38h+hKey]; hKey
0x1800604c8  lea     rdx, aExpectedvaluet; "ExpectedValueType"
0x1800604cf  call    cs:__imp_RegDeleteValueW
0x1800604d6  nop     dword ptr [rax+rax+00h]
0x1800604db  test    eax, eax
0x1800604dd  jnz     short loc_18006051C
0x1800604df  mov     rcx, [rsp+38h+hKey]; hKey
0x1800604e4  lea     rdx, aExpectedvalued; "ExpectedValueDataType"
0x1800604eb  call    cs:__imp_RegDeleteValueW
0x1800604f2  nop     dword ptr [rax+rax+00h]
0x1800604f7  test    eax, eax
0x1800604f9  jnz     short loc_18006051C
0x1800604fb  mov     rcx, [rsp+38h+hKey]; hKey
0x180060500  lea     rdx, aExpectedvalues; "ExpectedValueSemanticType"
0x180060507  call    cs:__imp_RegDeleteValueW
0x18006050e  nop     dword ptr [rax+rax+00h]
0x180060513  test    eax, 0FFFFFFFDh
0x180060518  jz      short loc_18006052B
0x18006051a  test    eax, eax
0x18006051c  jg      short loc_180060522
0x18006051e  mov     ebx, eax
0x180060520  jmp     short loc_18006052B
0x180060522  movzx   ebx, ax
0x180060525  or      ebx, 80070000h
0x18006052b  cmp     [rsp+38h+hKey], 0
0x180060531  jz      short loc_180060544
0x180060533  mov     rcx, [rsp+38h+hKey]; hKey
0x180060538  call    cs:__imp_RegCloseKey
0x18006053f  nop     dword ptr [rax+rax+00h]
0x180060544  mov     eax, ebx
0x180060546  add     rsp, 30h
0x18006054a  pop     rbx
0x18006054b  retn
```
