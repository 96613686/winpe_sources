# SetHiveLpacSecurity_(ushort const *,HKEY__ *,int,long (*)(HKEY__ *,void *,void *,int,int))

- ea: `0x18000df14`
- end: `0x18000df63`
- name: `?SetHiveLpacSecurity_@@YAJPEBGPEAUHKEY__@@HP6AJ1PEAX2HH@Z@Z`
- size: `79`
- prototype: `int __fastcall(const unsigned __int16 *, HKEY, int, int (*)(HKEY, void *, void *, int, int))`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000dd18`
- `0x18000e194`
- `0x1800123ac`

## callees

- `0x18000df14`
- `0x1800121fc`

## pseudocode

```c
int __fastcall SetHiveLpacSecurity_(
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
  v5 = v4 + 212;
  v6 = L"D:PAI(A;OICI;KA;;;%s)(A;OICI;KA;;;SY)(A;OICI;KA;;;BA)(A;OICI;KR;;;RC)(A;;KR;;;AC)(A;;KR;;;S-1-15-3-1024-106536593"
        "6-1281604716-3511738428-1654721687-432734479-3232135806-4053264122-3456934681)";
  if ( a3 )
    v6 = L"D:PAI(A;OICI;KA;;;%s)(A;OICI;KA;;;SY)(A;OICI;KA;;;BA)(A;OICI;KR;;;RC)(A;OICI;KR;;;AC)(A;OICI;KR;;;S-1-15-3-1024"
          "-1065365936-1281604716-3511738428-1654721687-432734479-3232135806-4053264122-3456934681)";
  return SetHiveSecurity_(
           a1,
           v6,
           L"D:AI(A;OICIID;KA;;;%s)(A;OICIID;KA;;;SY)(A;OICIID;KA;;;BA)(A;OICIID;KR;;;RC)(A;OICIID;KR;;;AC)(A;OICIID;KR;;;"
            "S-1-15-3-1024-1065365936-1281604716-3511738428-1654721687-432734479-3232135806-4053264122-3456934681)",
           v5,
           a2,
           a3,
           v9);
}

```

## disassembly

```asm
0x18000df14  sub     rsp, 48h
0x18000df18  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000df1c  mov     rax, rdx
0x18000df1f  xor     r11d, r11d
0x18000df22  inc     r9
0x18000df25  cmp     [rcx+r9*2], r11w
0x18000df2a  jnz     short loc_18000DF22
0x18000df2c  mov     [rsp+48h+var_20], r8d; int
0x18000df31  lea     r10, ?c_szNonInherited@?1??SetHiveLpacSecurity_@@YAJPEBGPEAUHKEY__@@HP6AJ1PEAX2HH@Z@Z@4QBGB; "D:PAI(A;OICI;KA;;;%s)(A;OICI;KA;;;SY)(A"...
0x18000df38  add     r9, 0D4h; unsigned __int64
0x18000df3f  mov     [rsp+48h+var_28], rax; HKEY
0x18000df44  test    r8d, r8d
0x18000df47  lea     rdx, ?c_szNonInheritable@?1??SetHiveLpacSecurity_@@YAJPEBGPEAUHKEY__@@HP6AJ1PEAX2HH@Z@Z@4QBGB; "D:PAI(A;OICI;KA;;;%s)(A;OICI;KA;;;SY)(A"...
0x18000df4e  lea     r8, ?c_szInherited@?1??SetHiveLpacSecurity_@@YAJPEBGPEAUHKEY__@@HP6AJ1PEAX2HH@Z@Z@4QBGB; "D:AI(A;OICIID;KA;;;%s)(A;OICIID;KA;;;SY"...
0x18000df55  cmovnz  rdx, r10; unsigned __int16 *
0x18000df59  call    ?SetHiveSecurity_@@YAJPEBG00_KPEAUHKEY__@@HP6AJ2PEAX3HH@Z@Z; SetHiveSecurity_(ushort const *,ushort const *,ushort const *,unsigned __int64,HKEY__ *,int,long (*)(HKEY__ *,void *,void *,int,int))
0x18000df5e  add     rsp, 48h
0x18000df62  retn
```
