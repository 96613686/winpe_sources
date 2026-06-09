# SetDefaultChangeOwnerHiveSecurity(ushort const *,ushort const *,HKEY__ *)

- ea: `0x1800486bc`
- end: `0x1800487e0`
- name: `?SetDefaultChangeOwnerHiveSecurity@@YAJPEBG0PEAUHKEY__@@@Z`
- size: `292`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, HKEY)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011200`
- `0x1800393e4`

## callees

- `0x180004170`
- `0x180012290`
- `0x1800220f0`
- `0x180035b60`
- `0x1800486bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800486fc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800486fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800487c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800487c7`

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
0x1800486bc  mov     r11, rsp
0x1800486bf  mov     [r11+8], rbx
0x1800486c3  push    rbp
0x1800486c4  push    rsi
0x1800486c5  push    rdi
0x1800486c6  push    r14
0x1800486c8  push    r15
0x1800486ca  sub     rsp, 40h
0x1800486ce  xor     r15d, r15d
0x1800486d1  mov     [r11+18h], r8
0x1800486d5  mov     [r11+20h], r15
0x1800486d9  mov     rdi, r8
0x1800486dc  mov     rsi, rdx
0x1800486df  mov     rbp, rcx
0x1800486e2  test    r8, r8
0x1800486e5  jnz     short loc_180048719
0x1800486e7  lea     rax, [r11+18h]
0x1800486eb  mov     r9d, 60019h; samDesired
0x1800486f1  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800486f8  mov     [r11-48h], rax
0x1800486fc  call    cs:__imp_RegOpenKeyExW
0x180048702  mov     ebx, eax
0x180048704  test    eax, eax
0x180048706  jle     short loc_180048711
0x180048708  movzx   ebx, ax
0x18004870b  or      ebx, 80070000h
0x180048711  test    ebx, ebx
0x180048713  js      loc_1800487BA
0x180048719  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004871d  mov     rcx, rax
0x180048720  inc     rcx
0x180048723  cmp     [rbp+rcx*2+0], r15w
0x180048729  jnz     short loc_180048720
0x18004872b  inc     rax
0x18004872e  cmp     [rsi+rax*2], r15w
0x180048733  jnz     short loc_18004872B
0x180048735  cmp     rcx, rax
0x180048738  lea     rdx, [rsp+68h+arg_18]; void **
0x180048740  cmovb   rcx, rax
0x180048744  lea     r14, [rcx+16h]
0x180048748  lea     rcx, [r14+r14]; dwBytes
0x18004874c  call    ?ResultFromHeapAlloc@@YAJ_KPEAPEAX@Z; ResultFromHeapAlloc(unsigned __int64,void * *)
0x180048751  mov     ebx, eax
0x180048753  test    eax, eax
0x180048755  js      short loc_1800487BA
0x180048757  mov     r9, rsi
0x18004875a  lea     r8, ?c_szSD@?1??SetDefaultChangeOwnerHiveSecurity@@YAJPEBG0PEAUHKEY__@@@Z@4QBGB; "D:PAI(A;OICI;KA;;;%s)"
0x180048761  mov     rsi, [rsp+68h+arg_18]
0x180048769  mov     rdx, r14; unsigned __int64
0x18004876c  mov     rcx, rsi; unsigned __int16 *
0x18004876f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180048774  mov     ebx, eax
0x180048776  test    eax, eax
0x180048778  js      short loc_1800487B2
0x18004877a  lea     rax, ?ApplyChangeSecurityToRegistryTree_@@YAJPEAUHKEY__@@PEAX1HH@Z; ApplyChangeSecurityToRegistryTree_(HKEY__ *,void *,void *,int,int)
0x180048781  mov     r9, r14; unsigned __int64
0x180048784  mov     [rsp+68h+var_38], rax; int (*)(HKEY, void *, void *, int, int)
0x180048789  lea     rdx, ?c_szSD@?1??SetDefaultChangeOwnerHiveSecurity@@YAJPEBG0PEAUHKEY__@@@Z@4QBGB; "D:PAI(A;OICI;KA;;;%s)"
0x180048790  mov     rax, [rsp+68h+hKey]
0x180048798  mov     r8, rsi; unsigned __int16 *
0x18004879b  mov     [rsp+68h+var_40], 1; int
0x1800487a3  mov     rcx, rbp; unsigned __int16 *
0x1800487a6  mov     [rsp+68h+var_48], rax; HKEY
0x1800487ab  call    ?SetHiveSecurity_@@YAJPEBG00_KPEAUHKEY__@@HP6AJ2PEAX3HH@Z@Z; SetHiveSecurity_(ushort const *,ushort const *,ushort const *,unsigned __int64,HKEY__ *,int,long (*)(HKEY__ *,void *,void *,int,int))
0x1800487b0  mov     ebx, eax
0x1800487b2  mov     rcx, rsi; lpMem
0x1800487b5  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x1800487ba  mov     rcx, [rsp+68h+hKey]; hKey
0x1800487c2  cmp     rcx, rdi
0x1800487c5  jz      short loc_1800487CD
0x1800487c7  call    cs:__imp_RegCloseKey
0x1800487cd  mov     eax, ebx
0x1800487cf  mov     rbx, [rsp+68h+arg_0]
0x1800487d4  add     rsp, 40h
0x1800487d8  pop     r15
0x1800487da  pop     r14
0x1800487dc  pop     rdi
0x1800487dd  pop     rsi
0x1800487de  pop     rbp
0x1800487df  retn
```
