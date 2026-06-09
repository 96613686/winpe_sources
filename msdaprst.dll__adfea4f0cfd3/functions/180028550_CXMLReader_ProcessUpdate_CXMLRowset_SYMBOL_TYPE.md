# CXMLReader::ProcessUpdate(CXMLRowset *,SYMBOL_TYPE)

- ea: `0x180028550`
- end: `0x1800286b5`
- name: `?ProcessUpdate@CXMLReader@@AEAAJPEAVCXMLRowset@@W4SYMBOL_TYPE@@@Z`
- size: `357`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x1800263a4`

## callees

- `0x1800263a4`
- `0x18002701c`
- `0x180028550`
- `0x180029dc0`

## pseudocode

```c
__int64 __fastcall CXMLReader::ProcessUpdate(__int64 a1, struct CXMLRowset *a2)
{
  __int64 *v2; // rax
  int v3; // r14d
  __int64 v6; // rsi
  unsigned int v7; // ebp
  unsigned int v8; // r15d
  __int64 v9; // rdi
  int v10; // eax
  unsigned int v11; // r8d
  unsigned __int16 *v12; // rdx
  CCollectionList *v13; // rcx
  bool v14; // zf
  unsigned __int64 v16; // [rsp+40h] [rbp-48h] BYREF
  int v17; // [rsp+48h] [rbp-40h]
  int v18; // [rsp+4Ch] [rbp-3Ch]
  __int64 v19; // [rsp+50h] [rbp-38h]
  unsigned __int64 v20; // [rsp+90h] [rbp+8h] BYREF

  v2 = *(__int64 **)(a1 + 424);
  v3 = 0;
  v6 = *v2;
  v7 = 1;
  v8 = *(_DWORD *)(*v2 + 24);
  *(_DWORD *)(a1 + 476) = 8;
  while ( v7 < v8 )
  {
    v9 = *(_QWORD *)(*(_QWORD *)(a1 + 424) + 8LL * v7);
    if ( *(_QWORD *)(v9 + 16) == v6 && *(_DWORD *)(v9 + 8) == 1 )
    {
      if ( CXMLReader::IsMatch(
             a1,
             *(unsigned __int16 **)(v9 + 32),
             *(_DWORD *)v9,
             *(_DWORD *)(v9 + 4),
             (wchar_t *)&wszOriginal,
             8,
             3) )
      {
        v6 = v9;
      }
      else
      {
        v10 = *(_DWORD *)(v9 + 44);
        v11 = *(_DWORD *)v9;
        v12 = *(unsigned __int16 **)(v9 + 32);
        v18 = 0;
        v16 = 0;
        v20 = 0;
        v13 = *(CCollectionList **)(a1 + 136);
        v19 = v9;
        v17 = v10;
        CCollectionList::LookUpByKey(v13, v12, v11, &v20);
        *(_QWORD *)(a1 + 456) = v20;
        *(_QWORD *)(a1 + 136) = *((_QWORD *)a2 + 79);
        v3 = CXMLReader::Fetch((CXMLReader *)a1, a2, (__int64)&v16);
        if ( v3 < 0 )
          return (unsigned int)v3;
        v14 = *(_DWORD *)(a1 + 476) == 8;
        *(_QWORD *)(a1 + 136) = *(_QWORD *)(*(_QWORD *)(a1 + 136) + 48LL);
        if ( v14 )
        {
          *(_DWORD *)(a1 + 476) = 2;
          v6 = *(_QWORD *)(v6 + 16);
        }
      }
    }
    ++v7;
  }
  *(_DWORD *)(a1 + 476) = 8;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180028550  mov     [rsp+arg_8], rbx
0x180028555  mov     [rsp+arg_10], rbp
0x18002855a  push    rsi
0x18002855b  push    rdi
0x18002855c  push    r13
0x18002855e  push    r14
0x180028560  push    r15
0x180028562  sub     rsp, 60h
0x180028566  mov     rax, [rcx+1A8h]
0x18002856d  xor     r14d, r14d
0x180028570  mov     r13, rdx
0x180028573  mov     rbx, rcx
0x180028576  mov     rsi, [rax]
0x180028579  lea     ebp, [r14+1]
0x18002857d  mov     r15d, [rsi+18h]
0x180028581  mov     dword ptr [rcx+1DCh], 8
0x18002858b  cmp     ebp, r15d
0x18002858e  jnb     loc_18002868E
0x180028594  mov     rax, [rbx+1A8h]
0x18002859b  mov     ecx, ebp
0x18002859d  mov     rdi, [rax+rcx*8]
0x1800285a1  cmp     [rdi+10h], rsi
0x1800285a5  jnz     loc_180028687
0x1800285ab  cmp     dword ptr [rdi+8], 1
0x1800285af  jnz     loc_180028687
0x1800285b5  mov     r9d, [rdi+4]
0x1800285b9  lea     rax, ?wszOriginal@@3PAGA; "original"
0x1800285c0  mov     r8d, [rdi]
0x1800285c3  mov     rcx, rbx
0x1800285c6  mov     rdx, [rdi+20h]
0x1800285ca  mov     [rsp+88h+var_58], 3
0x1800285d2  mov     [rsp+88h+var_60], 8
0x1800285da  mov     [rsp+88h+var_68], rax
0x1800285df  call    ?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z; CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)
0x1800285e4  xor     ecx, ecx
0x1800285e6  test    al, al
0x1800285e8  jz      short loc_1800285F2
0x1800285ea  mov     rsi, rdi
0x1800285ed  jmp     loc_180028687
0x1800285f2  mov     eax, [rdi+2Ch]
0x1800285f5  lea     r9, [rsp+88h+arg_0]; unsigned __int64 *
0x1800285fd  mov     r8d, [rdi]; unsigned int
0x180028600  mov     rdx, [rdi+20h]; unsigned __int16 *
0x180028604  mov     [rsp+88h+var_3C], ecx
0x180028608  mov     [rsp+88h+var_48], rcx
0x18002860d  mov     [rsp+88h+arg_0], rcx
0x180028615  mov     rcx, [rbx+88h]; this
0x18002861c  mov     [rsp+88h+var_38], rdi
0x180028621  mov     [rsp+88h+var_40], eax
0x180028625  call    ?LookUpByKey@CCollectionList@@QEAAJPEAGKPEA_K@Z; CCollectionList::LookUpByKey(ushort *,ulong,unsigned __int64 *)
0x18002862a  mov     rax, [rsp+88h+arg_0]
0x180028632  lea     r8, [rsp+88h+var_48]; unsigned __int64
0x180028637  mov     [rbx+1C8h], rax
0x18002863e  mov     rdx, r13; struct CXMLRowset *
0x180028641  mov     rax, [r13+278h]
0x180028648  mov     rcx, rbx; this
0x18002864b  mov     [rbx+88h], rax
0x180028652  call    ?Fetch@CXMLReader@@QEAAJPEAVCXMLRowset@@_K@Z; CXMLReader::Fetch(CXMLRowset *,unsigned __int64)
0x180028657  mov     r14d, eax
0x18002865a  test    eax, eax
0x18002865c  js      short loc_180028698
0x18002865e  cmp     dword ptr [rbx+1DCh], 8
0x180028665  mov     rcx, [rbx+88h]
0x18002866c  mov     rdx, [rcx+30h]
0x180028670  mov     [rbx+88h], rdx
0x180028677  jnz     short loc_180028687
0x180028679  mov     dword ptr [rbx+1DCh], 2
0x180028683  mov     rsi, [rsi+10h]
0x180028687  inc     ebp
0x180028689  jmp     loc_18002858B
0x18002868e  mov     dword ptr [rbx+1DCh], 8
0x180028698  lea     r11, [rsp+88h+var_28]
0x18002869d  mov     eax, r14d
0x1800286a0  mov     rbx, [r11+38h]
0x1800286a4  mov     rbp, [r11+40h]
0x1800286a8  mov     rsp, r11
0x1800286ab  pop     r15
0x1800286ad  pop     r14
0x1800286af  pop     r13
0x1800286b1  pop     rdi
0x1800286b2  pop     rsi
0x1800286b3  retn
```
