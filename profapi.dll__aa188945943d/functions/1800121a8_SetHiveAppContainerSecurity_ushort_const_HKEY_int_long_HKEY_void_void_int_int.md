# SetHiveAppContainerSecurity_(ushort const *,HKEY__ *,int,long (*)(HKEY__ *,void *,void *,int,int))

- ea: `0x1800121a8`
- end: `0x1800121f4`
- name: `?SetHiveAppContainerSecurity_@@YAJPEBGPEAUHKEY__@@HP6AJ1PEAX2HH@Z@Z`
- size: `76`
- prototype: `int __fastcall(const unsigned __int16 *, HKEY, int, int (*)(HKEY, void *, void *, int, int))`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e194`

## callees

- `0x1800121a8`
- `0x1800121fc`

## pseudocode

```c
int __fastcall SetHiveAppContainerSecurity_(
        const unsigned __int16 *a1,
        HKEY a2,
        int a3,
        int (*a4)(HKEY, void *, void *, int, int))
{
  __int64 v4; // r9
  unsigned __int64 v5; // r9
  const unsigned __int16 *v6; // rdx
  int (*v9)(HKEY, void *, void *, int, int); // [rsp+30h] [rbp-18h]

  v4 = -1;
  do
    ++v4;
  while ( a1[v4] );
  v5 = v4 + 96;
  v6 = L"D:PAI(A;OICI;KA;;;%s)(A;OICI;KA;;;SY)(A;OICI;KA;;;BA)(A;OICI;KR;;;RC)(A;;KR;;;AC)";
  if ( a3 )
    v6 = L"D:PAI(A;OICI;KA;;;%s)(A;OICI;KA;;;SY)(A;OICI;KA;;;BA)(A;OICI;KR;;;RC)(A;OICI;KR;;;AC)";
  return SetHiveSecurity_(
           a1,
           v6,
           L"D:AI(A;OICIID;KA;;;%s)(A;OICIID;KA;;;SY)(A;OICIID;KA;;;BA)(A;OICIID;KR;;;RC)(A;OICIID;KR;;;AC)",
           v5,
           a2,
           a3,
           v9);
}

```

## disassembly

```asm
0x1800121a8  sub     rsp, 48h
0x1800121ac  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800121b0  mov     rax, rdx
0x1800121b3  xor     r11d, r11d
0x1800121b6  inc     r9
0x1800121b9  cmp     [rcx+r9*2], r11w
0x1800121be  jnz     short loc_1800121B6
0x1800121c0  mov     [rsp+48h+var_20], r8d; int
0x1800121c5  lea     r10, ?c_szNonInherited@?1??SetHiveAppContainerSecurity_@@YAJPEBGPEAUHKEY__@@HP6AJ1PEAX2HH@Z@Z@4QBGB; "D:PAI(A;OICI;KA;;;%s)(A;OICI;KA;;;SY)(A"...
0x1800121cc  add     r9, 60h ; '`'; unsigned __int64
0x1800121d0  mov     [rsp+48h+var_28], rax; HKEY
0x1800121d5  test    r8d, r8d
0x1800121d8  lea     rdx, ?c_szNonInheritable@?1??SetHiveAppContainerSecurity_@@YAJPEBGPEAUHKEY__@@HP6AJ1PEAX2HH@Z@Z@4QBGB; "D:PAI(A;OICI;KA;;;%s)(A;OICI;KA;;;SY)(A"...
0x1800121df  lea     r8, ?c_szInherited@?1??SetHiveAppContainerSecurity_@@YAJPEBGPEAUHKEY__@@HP6AJ1PEAX2HH@Z@Z@4QBGB; "D:AI(A;OICIID;KA;;;%s)(A;OICIID;KA;;;SY"...
0x1800121e6  cmovnz  rdx, r10; unsigned __int16 *
0x1800121ea  call    ?SetHiveSecurity_@@YAJPEBG00_KPEAUHKEY__@@HP6AJ2PEAX3HH@Z@Z; SetHiveSecurity_(ushort const *,ushort const *,ushort const *,unsigned __int64,HKEY__ *,int,long (*)(HKEY__ *,void *,void *,int,int))
0x1800121ef  add     rsp, 48h
0x1800121f3  retn
```
