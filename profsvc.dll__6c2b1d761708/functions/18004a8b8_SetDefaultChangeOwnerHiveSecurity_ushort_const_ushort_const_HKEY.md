# SetDefaultChangeOwnerHiveSecurity(ushort const *,ushort const *,HKEY__ *)

- ea: `0x18004a8b8`
- end: `0x18004a9e9`
- name: `?SetDefaultChangeOwnerHiveSecurity@@YAJPEBG0PEAUHKEY__@@@Z`
- size: `305`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, HKEY)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016150`
- `0x18002f844`

## callees

- `0x180005370`
- `0x1800172e0`
- `0x1800250b0`
- `0x180036080`
- `0x18004a8b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004a8f8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004a8f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a9c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a9c9`

## pseudocode

```c
__int64 __fastcall SetDefaultChangeOwnerHiveSecurity(const unsigned __int16 *a1, const unsigned __int16 *a2, HKEY a3)
{
  LSTATUS v6; // eax
  int v7; // ebx
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // r14
  const unsigned __int16 *v11; // r9
  unsigned __int16 *v12; // rsi
  HKEY hKey; // [rsp+80h] [rbp+18h] BYREF
  unsigned __int16 *v15; // [rsp+88h] [rbp+20h] BYREF

  hKey = a3;
  v15 = 0;
  if ( a3 )
    goto LABEL_5;
  v6 = RegOpenKeyExW(HKEY_USERS, a2, 0, 0x60019u, &hKey);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 >= 0 )
  {
LABEL_5:
    v8 = -1;
    v9 = -1;
    do
      ++v9;
    while ( a1[v9] );
    do
      ++v8;
    while ( a2[v8] );
    if ( v9 < v8 )
      v9 = v8;
    v10 = v9 + 22;
    v7 = ResultFromHeapAlloc(2 * (v9 + 22), (void **)&v15);
    if ( v7 >= 0 )
    {
      v11 = a2;
      v12 = v15;
      v7 = StringCchPrintfW(v15, v10, L"D:PAI(A;OICI;KA;;;%s)", v11);
      if ( v7 >= 0 )
        v7 = SetHiveSecurity_(
               a1,
               L"D:PAI(A;OICI;KA;;;%s)",
               v12,
               v10,
               hKey,
               1,
               (int (*)(HKEY, void *, void *, int, int))ApplyChangeSecurityToRegistryTree_);
      ResultFromHeapFree(v12);
    }
  }
  if ( hKey != a3 )
    RegCloseKey(hKey);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18004a8b8  mov     r11, rsp
0x18004a8bb  mov     [r11+8], rbx
0x18004a8bf  push    rbp
0x18004a8c0  push    rsi
0x18004a8c1  push    rdi
0x18004a8c2  push    r14
0x18004a8c4  push    r15
0x18004a8c6  sub     rsp, 40h
0x18004a8ca  xor     r15d, r15d
0x18004a8cd  mov     [r11+18h], r8
0x18004a8d1  mov     [r11+20h], r15
0x18004a8d5  mov     rdi, r8
0x18004a8d8  mov     rsi, rdx
0x18004a8db  mov     rbp, rcx
0x18004a8de  test    r8, r8
0x18004a8e1  jnz     short loc_18004A91B
0x18004a8e3  lea     rax, [r11+18h]
0x18004a8e7  mov     r9d, 60019h; samDesired
0x18004a8ed  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18004a8f4  mov     [r11-48h], rax
0x18004a8f8  call    cs:__imp_RegOpenKeyExW
0x18004a8ff  nop     dword ptr [rax+rax+00h]
0x18004a904  mov     ebx, eax
0x18004a906  test    eax, eax
0x18004a908  jle     short loc_18004A913
0x18004a90a  movzx   ebx, ax
0x18004a90d  or      ebx, 80070000h
0x18004a913  test    ebx, ebx
0x18004a915  js      loc_18004A9BC
0x18004a91b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004a91f  mov     rcx, rax
0x18004a922  inc     rcx
0x18004a925  cmp     [rbp+rcx*2+0], r15w
0x18004a92b  jnz     short loc_18004A922
0x18004a92d  inc     rax
0x18004a930  cmp     [rsi+rax*2], r15w
0x18004a935  jnz     short loc_18004A92D
0x18004a937  cmp     rcx, rax
0x18004a93a  lea     rdx, [rsp+68h+arg_18]; void **
0x18004a942  cmovb   rcx, rax
0x18004a946  lea     r14, [rcx+16h]
0x18004a94a  lea     rcx, [r14+r14]; dwBytes
0x18004a94e  call    ?ResultFromHeapAlloc@@YAJ_KPEAPEAX@Z; ResultFromHeapAlloc(unsigned __int64,void * *)
0x18004a953  mov     ebx, eax
0x18004a955  test    eax, eax
0x18004a957  js      short loc_18004A9BC
0x18004a959  mov     r9, rsi
0x18004a95c  lea     r8, ?c_szSD@?1??SetDefaultChangeOwnerHiveSecurity@@YAJPEBG0PEAUHKEY__@@@Z@4QBGB; "D:PAI(A;OICI;KA;;;%s)"
0x18004a963  mov     rsi, [rsp+68h+arg_18]
0x18004a96b  mov     rdx, r14; unsigned __int64
0x18004a96e  mov     rcx, rsi; unsigned __int16 *
0x18004a971  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004a976  mov     ebx, eax
0x18004a978  test    eax, eax
0x18004a97a  js      short loc_18004A9B4
0x18004a97c  lea     rax, ?ApplyChangeSecurityToRegistryTree_@@YAJPEAUHKEY__@@PEAX1HH@Z; ApplyChangeSecurityToRegistryTree_(HKEY__ *,void *,void *,int,int)
0x18004a983  mov     r9, r14; unsigned __int64
0x18004a986  mov     [rsp+68h+var_38], rax; int (*)(HKEY, void *, void *, int, int)
0x18004a98b  lea     rdx, ?c_szSD@?1??SetDefaultChangeOwnerHiveSecurity@@YAJPEBG0PEAUHKEY__@@@Z@4QBGB; "D:PAI(A;OICI;KA;;;%s)"
0x18004a992  mov     rax, [rsp+68h+hKey]
0x18004a99a  mov     r8, rsi; unsigned __int16 *
0x18004a99d  mov     [rsp+68h+var_40], 1; int
0x18004a9a5  mov     rcx, rbp; unsigned __int16 *
0x18004a9a8  mov     [rsp+68h+var_48], rax; HKEY
0x18004a9ad  call    ?SetHiveSecurity_@@YAJPEBG00_KPEAUHKEY__@@HP6AJ2PEAX3HH@Z@Z; SetHiveSecurity_(ushort const *,ushort const *,ushort const *,unsigned __int64,HKEY__ *,int,long (*)(HKEY__ *,void *,void *,int,int))
0x18004a9b2  mov     ebx, eax
0x18004a9b4  mov     rcx, rsi; lpMem
0x18004a9b7  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x18004a9bc  mov     rcx, [rsp+68h+hKey]; hKey
0x18004a9c4  cmp     rcx, rdi
0x18004a9c7  jz      short loc_18004A9D5
0x18004a9c9  call    cs:__imp_RegCloseKey
0x18004a9d0  nop     dword ptr [rax+rax+00h]
0x18004a9d5  mov     eax, ebx
0x18004a9d7  mov     rbx, [rsp+68h+arg_0]
0x18004a9dc  add     rsp, 40h
0x18004a9e0  pop     r15
0x18004a9e2  pop     r14
0x18004a9e4  pop     rdi
0x18004a9e5  pop     rsi
0x18004a9e6  pop     rbp
0x18004a9e7  retn
```
