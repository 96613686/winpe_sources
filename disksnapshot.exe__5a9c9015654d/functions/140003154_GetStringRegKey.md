# GetStringRegKey

- ea: `0x140003154`
- end: `0x1400032bb`
- name: `GetStringRegKey`
- size: `359`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, const WCHAR *, char *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400032c4`

## callees

- `0x140001c50`
- `0x1400027c6`
- `0x1400027d2`
- `0x140002d90`
- `0x140003154`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003294`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003294`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000322d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000322d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400031e1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400031e1`

## pseudocode

```c
__int64 __fastcall GetStringRegKey(__int64 a1, const WCHAR *a2, const WCHAR *a3, char *a4)
{
  char *v7; // rcx
  unsigned __int64 *v8; // r14
  LSTATUS v9; // eax
  unsigned int v10; // edi
  bool v11; // cc
  __int64 v12; // r8
  unsigned __int64 v13; // rdx
  __int64 v14; // rbx
  DWORD cbData; // [rsp+30h] [rbp-258h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-250h] BYREF
  _WORD Data[264]; // [rsp+40h] [rbp-248h] BYREF

  hKey = 0;
  memset_0(Data, 0, 0x208u);
  v11 = *((_QWORD *)a4 + 3) <= 7u;
  cbData = 520;
  if ( v11 )
    v7 = a4;
  else
    v7 = *(char **)a4;
  v8 = (unsigned __int64 *)(a4 + 16);
  *((_QWORD *)a4 + 2) = 0;
  *(_WORD *)v7 = 0;
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(const WCHAR **)a2;
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x20019u, &hKey);
  v10 = v9;
  v11 = v9 <= 0;
  if ( v9 )
    goto LABEL_7;
  if ( *((_QWORD *)a3 + 3) > 7u )
    a3 = *(const WCHAR **)a3;
  v9 = RegQueryValueExW(hKey, a3, 0, 0, (LPBYTE)Data, &cbData);
  v10 = v9;
  v11 = v9 <= 0;
  if ( v9 )
  {
LABEL_7:
    if ( !v11 )
      v10 = (unsigned __int16)v9 | 0x80070000;
  }
  else
  {
    v10 = 0;
    v13 = -1;
    do
      ++v13;
    while ( Data[v13] );
    if ( v13 > *((_QWORD *)a4 + 3) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char **)a4,
        v13,
        v12,
        Data);
    }
    else
    {
      if ( *((_QWORD *)a4 + 3) > 7u )
        a4 = *(char **)a4;
      v14 = 2 * v13;
      *v8 = v13;
      memmove_0(a4, Data, 2 * v13);
      *(_WORD *)&a4[v14] = 0;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v10;
}

```

## disassembly

```asm
0x140003154  push    rbx
0x140003156  push    rsi
0x140003157  push    rdi
0x140003158  push    r14
0x14000315a  push    r15
0x14000315c  sub     rsp, 260h
0x140003163  mov     rax, cs:__security_cookie
0x14000316a  xor     rax, rsp
0x14000316d  mov     [rsp+288h+var_38], rax
0x140003175  mov     rbx, r8
0x140003178  lea     rcx, [rsp+288h+Data]; void *
0x14000317d  mov     rdi, rdx
0x140003180  xor     r15d, r15d
0x140003183  xor     edx, edx; Val
0x140003185  mov     [rsp+288h+hKey], r15
0x14000318a  mov     r8d, 208h; Size
0x140003190  mov     rsi, r9
0x140003193  call    memset_0
0x140003198  cmp     qword ptr [rsi+18h], 7
0x14000319d  mov     [rsp+288h+cbData], 208h
0x1400031a5  jbe     short loc_1400031AC
0x1400031a7  mov     rcx, [rsi]
0x1400031aa  jmp     short loc_1400031AF
0x1400031ac  mov     rcx, rsi
0x1400031af  lea     r14, [rsi+10h]
0x1400031b3  mov     [r14], r15
0x1400031b6  mov     [rcx], r15w
0x1400031ba  cmp     qword ptr [rdi+18h], 7
0x1400031bf  jbe     short loc_1400031C4
0x1400031c1  mov     rdi, [rdi]
0x1400031c4  lea     rax, [rsp+288h+hKey]
0x1400031c9  mov     r9d, 20019h; samDesired
0x1400031cf  xor     r8d, r8d; ulOptions
0x1400031d2  mov     [rsp+288h+phkResult], rax; phkResult
0x1400031d7  mov     rdx, rdi; lpSubKey
0x1400031da  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400031e1  call    cs:__imp_RegOpenKeyExW
0x1400031e7  mov     edi, eax
0x1400031e9  test    eax, eax
0x1400031eb  jz      short loc_140003201
0x1400031ed  jle     loc_14000328A
0x1400031f3  movzx   edi, ax
0x1400031f6  or      edi, 80070000h
0x1400031fc  jmp     loc_14000328A
0x140003201  cmp     qword ptr [rbx+18h], 7
0x140003206  jbe     short loc_14000320B
0x140003208  mov     rbx, [rbx]
0x14000320b  mov     rcx, [rsp+288h+hKey]; hKey
0x140003210  lea     rax, [rsp+288h+cbData]
0x140003215  mov     [rsp+288h+lpcbData], rax; lpcbData
0x14000321a  xor     r9d, r9d; lpType
0x14000321d  lea     rax, [rsp+288h+Data]
0x140003222  xor     r8d, r8d; lpReserved
0x140003225  mov     rdx, rbx; lpValueName
0x140003228  mov     [rsp+288h+phkResult], rax; lpData
0x14000322d  call    cs:__imp_RegQueryValueExW
0x140003233  mov     edi, eax
0x140003235  test    eax, eax
0x140003237  jnz     short loc_1400031ED
0x140003239  mov     edi, r15d
0x14000323c  lea     rax, [rsp+288h+Data]
0x140003241  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140003245  inc     rdx
0x140003248  cmp     [rax+rdx*2], r15w
0x14000324d  jnz     short loc_140003245
0x14000324f  cmp     rdx, [rsi+18h]
0x140003253  ja      short loc_14000327D
0x140003255  cmp     qword ptr [rsi+18h], 7
0x14000325a  jbe     short loc_14000325F
0x14000325c  mov     rsi, [rsi]
0x14000325f  lea     rbx, [rdx+rdx]
0x140003263  mov     [r14], rdx
0x140003266  mov     r8, rbx; Size
0x140003269  lea     rdx, [rsp+288h+Data]; Src
0x14000326e  mov     rcx, rsi; void *
0x140003271  call    memmove_0
0x140003276  mov     [rbx+rsi], r15w
0x14000327b  jmp     short loc_14000328A
0x14000327d  lea     r9, [rsp+288h+Data]
0x140003282  mov     rcx, rsi
0x140003285  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x14000328a  mov     rcx, [rsp+288h+hKey]; hKey
0x14000328f  test    rcx, rcx
0x140003292  jz      short loc_14000329A
0x140003294  call    cs:__imp_RegCloseKey
0x14000329a  mov     eax, edi
0x14000329c  mov     rcx, [rsp+288h+var_38]
0x1400032a4  xor     rcx, rsp; StackCookie
0x1400032a7  call    __security_check_cookie
0x1400032ac  add     rsp, 260h
0x1400032b3  pop     r15
0x1400032b5  pop     r14
0x1400032b7  pop     rdi
0x1400032b8  pop     rsi
0x1400032b9  pop     rbx
0x1400032ba  retn
```
