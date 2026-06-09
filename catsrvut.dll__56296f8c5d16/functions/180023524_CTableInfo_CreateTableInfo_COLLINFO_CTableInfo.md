# CTableInfo::CreateTableInfo(COLLINFO *,CTableInfo * &)

- ea: `0x180023524`
- end: `0x1800236ff`
- name: `?CreateTableInfo@CTableInfo@@SAJPEAUCOLLINFO@@AEAPEAV1@@Z`
- size: `475`
- prototype: `__int64 __fastcall(struct COLLINFO *, struct CTableInfo **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180023708`

## callees

- `0x180006980`
- `0x180021c34`
- `0x180023524`
- `0x180023834`
- `0x180023aa8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023545`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023681`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023545`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023681`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CTableInfo::CreateTableInfo(struct COLLINFO *a1, struct CTableInfo **a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rbx
  int v7; // edi
  int i; // ebx
  CTableInfo *v9; // rbp
  __int64 v10; // r13
  __int64 v11; // rcx
  __int64 v12; // rcx
  _QWORD *v13; // rdx
  LPVOID v14; // rax
  CTableInfo *v15; // r8
  int j; // edx
  __int64 v17; // rax
  int v18; // r9d
  _QWORD *v19; // [rsp+58h] [rbp+10h] BYREF
  _QWORD *v20; // [rsp+60h] [rbp+18h] BYREF

  v4 = CoTaskMemAlloc(0x40u);
  v5 = v4;
  v19 = v4;
  if ( v4 )
  {
    v20 = v4;
    *v4 = 0;
    v4[1] = 17;
    v4[2] = 0;
    v4[4] = v4 + 3;
    v4[3] = v4 + 3;
    Map<unsigned short const *,HKEY__ *,HashWSTR,EmptyMapBase>::allocAssocIfNecessary((__int64)v4);
    v5[7] = 0;
    v5[5] = 0;
    *((_DWORD *)v5 + 12) = 0;
  }
  else
  {
    v5 = 0;
  }
  *a2 = (struct CTableInfo *)v5;
  if ( !v5 )
    return 2147942414LL;
  v7 = 0;
  v5[5] = a1;
  for ( i = 0; ; ++i )
  {
    v9 = *a2;
    if ( i >= *((_DWORD *)a1 + 8) )
      break;
    v19 = 0;
    v10 = *((_QWORD *)a1 + 3) + 40LL * i;
    if ( (unsigned int)Map<unsigned long,MyDataEntry *,HashULONG,EmptyMapBase>::find(v9, v10 + 16, &v19) )
      continue;
    v20 = (_QWORD *)v10;
    v7 = Map<unsigned short const *,HKEY__ *,HashWSTR,EmptyMapBase>::allocAssocIfNecessary(v11);
    if ( v7 >= 0 )
    {
      v19 = 0;
      if ( (unsigned int)Map<unsigned long,MyDataEntry *,HashULONG,EmptyMapBase>::find(v9, v10 + 16, &v19) )
      {
        v13 = v19;
        *(_DWORD *)(*v19 + 28LL) = *(_DWORD *)(v10 + 16);
        *(_QWORD *)(*v13 + 32LL) = v10;
        continue;
      }
      v7 = Map<unsigned long,MyDataEntry *,HashULONG,EmptyMapBase>::newAssoc(v12, v10 + 16, &v20, v19);
    }
    if ( v7 < 0 )
      goto LABEL_23;
  }
  *((_DWORD *)v9 + 12) = 0;
  v14 = CoTaskMemAlloc(saturated_mul(*((int *)a1 + 22), 4u));
  v15 = *a2;
  *((_QWORD *)*a2 + 7) = v14;
  if ( !v14 )
  {
    v7 = -2147024882;
LABEL_23:
    if ( *a2 )
      CTableInfo::`scalar deleting destructor'(*a2);
    return (unsigned int)v7;
  }
  for ( j = 0; j < *((_DWORD *)a1 + 22); ++j )
  {
    v17 = *((_QWORD *)a1 + 10);
    if ( !*(_QWORD *)(v17 + 24LL * j) )
    {
      v18 = *(_DWORD *)(v17 + 24LL * j + 12);
      if ( v18 != -1 )
        *(_DWORD *)(*((_QWORD *)v15 + 7) + 4LL * (unsigned int)(*((_DWORD *)v15 + 12))++) = v18;
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180023524  mov     [rsp+arg_0], rbx
0x180023529  mov     [rsp+arg_18], rbp
0x18002352e  push    rsi
0x18002352f  push    rdi
0x180023530  push    r13
0x180023532  push    r14
0x180023534  push    r15
0x180023536  sub     rsp, 20h
0x18002353a  mov     r14, rdx
0x18002353d  mov     rsi, rcx
0x180023540  mov     ecx, 40h ; '@'; cb
0x180023545  call    cs:__imp_CoTaskMemAlloc
0x18002354b  mov     rbx, rax
0x18002354e  mov     [rsp+48h+arg_8], rax
0x180023553  test    rax, rax
0x180023556  jz      short loc_1800235A1
0x180023558  mov     [rsp+48h+arg_10], rax
0x18002355d  mov     qword ptr [rax], 0
0x180023564  mov     qword ptr [rax+8], 11h
0x18002356c  mov     qword ptr [rax+10h], 0
0x180023574  lea     rcx, [rax+18h]
0x180023578  mov     [rcx+8], rcx
0x18002357c  mov     [rcx], rcx
0x18002357f  mov     rcx, rax
0x180023582  call    ?allocAssocIfNecessary@?$Map@PEBGPEAUHKEY__@@VHashWSTR@@VEmptyMapBase@@@@AEAAJXZ; Map<ushort const *,HKEY__ *,HashWSTR,EmptyMapBase>::allocAssocIfNecessary(void)
0x180023587  nop
0x180023588  mov     qword ptr [rbx+38h], 0
0x180023590  mov     qword ptr [rbx+28h], 0
0x180023598  mov     dword ptr [rbx+30h], 0
0x18002359f  jmp     short loc_1800235A3
0x1800235a1  xor     ebx, ebx
0x1800235a3  mov     [r14], rbx
0x1800235a6  test    rbx, rbx
0x1800235a9  jnz     short loc_1800235B5
0x1800235ab  mov     eax, 8007000Eh
0x1800235b0  jmp     loc_1800236E8
0x1800235b5  xor     edi, edi
0x1800235b7  mov     [rbx+28h], rsi
0x1800235bb  xor     ebx, ebx
0x1800235bd  mov     rbp, [r14]
0x1800235c0  cmp     ebx, [rsi+20h]
0x1800235c3  jge     loc_180023660
0x1800235c9  mov     [rsp+48h+arg_8], 0
0x1800235d2  movsxd  rax, ebx
0x1800235d5  lea     rcx, [rax+rax*4]
0x1800235d9  mov     rax, [rsi+18h]
0x1800235dd  lea     r13, [rax+rcx*8]
0x1800235e1  lea     r15, [r13+10h]
0x1800235e5  lea     r8, [rsp+48h+arg_8]
0x1800235ea  mov     rdx, r15
0x1800235ed  mov     rcx, rbp
0x1800235f0  call    ?find@?$Map@KPEAUMyDataEntry@@VHashULONG@@VEmptyMapBase@@@@AEBAHAEBKPEAPEAPEAVAssoc@1@@Z; Map<ulong,MyDataEntry *,HashULONG,EmptyMapBase>::find(ulong const &,Map<ulong,MyDataEntry *,HashULONG,EmptyMapBase>::Assoc * * *)
0x1800235f5  test    eax, eax
0x1800235f7  jnz     short loc_180023659
0x1800235f9  mov     [rsp+48h+arg_10], r13
0x1800235fe  call    ?allocAssocIfNecessary@?$Map@PEBGPEAUHKEY__@@VHashWSTR@@VEmptyMapBase@@@@AEAAJXZ; Map<ushort const *,HKEY__ *,HashWSTR,EmptyMapBase>::allocAssocIfNecessary(void)
0x180023603  mov     edi, eax
0x180023605  test    eax, eax
0x180023607  js      short loc_180023651
0x180023609  mov     [rsp+48h+arg_8], 0
0x180023612  lea     r8, [rsp+48h+arg_8]
0x180023617  mov     rdx, r15
0x18002361a  mov     rcx, rbp
0x18002361d  call    ?find@?$Map@KPEAUMyDataEntry@@VHashULONG@@VEmptyMapBase@@@@AEBAHAEBKPEAPEAPEAVAssoc@1@@Z; Map<ulong,MyDataEntry *,HashULONG,EmptyMapBase>::find(ulong const &,Map<ulong,MyDataEntry *,HashULONG,EmptyMapBase>::Assoc * * *)
0x180023622  test    eax, eax
0x180023624  jz      short loc_18002363D
0x180023626  mov     rdx, [rsp+48h+arg_8]
0x18002362b  mov     rcx, [rdx]
0x18002362e  mov     eax, [r15]
0x180023631  mov     [rcx+1Ch], eax
0x180023634  mov     rax, [rdx]
0x180023637  mov     [rax+20h], r13
0x18002363b  jmp     short loc_180023659
0x18002363d  mov     r9, [rsp+48h+arg_8]
0x180023642  lea     r8, [rsp+48h+arg_10]
0x180023647  mov     rdx, r15
0x18002364a  call    ?newAssoc@?$Map@KPEAUMyDataEntry@@VHashULONG@@VEmptyMapBase@@@@AEAAJAEBKAEBQEAUMyDataEntry@@PEAPEAVAssoc@1@@Z; Map<ulong,MyDataEntry *,HashULONG,EmptyMapBase>::newAssoc(ulong const &,MyDataEntry * const &,Map<ulong,MyDataEntry *,HashULONG,EmptyMapBase>::Assoc * *)
0x18002364f  mov     edi, eax
0x180023651  test    edi, edi
0x180023653  js      loc_1800236D9
0x180023659  inc     ebx
0x18002365b  jmp     loc_1800235BD
0x180023660  mov     dword ptr [rbp+30h], 0
0x180023667  movsxd  rcx, dword ptr [rsi+58h]
0x18002366b  mov     eax, 4
0x180023670  mul     rcx
0x180023673  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002367a  cmovb   rax, rcx
0x18002367e  mov     rcx, rax; cb
0x180023681  call    cs:__imp_CoTaskMemAlloc
0x180023687  mov     r8, [r14]
0x18002368a  mov     [r8+38h], rax
0x18002368e  test    rax, rax
0x180023691  jnz     short loc_18002369A
0x180023693  mov     edi, 8007000Eh
0x180023698  jmp     short loc_1800236D9
0x18002369a  xor     edx, edx
0x18002369c  cmp     [rsi+58h], edx
0x18002369f  jle     short loc_1800236D5
0x1800236a1  movsxd  rax, edx
0x1800236a4  lea     r9, [rax+rax*2]
0x1800236a8  mov     rax, [rsi+50h]
0x1800236ac  cmp     qword ptr [rax+r9*8], 0
0x1800236b1  jnz     short loc_1800236CE
0x1800236b3  mov     r9d, [rax+r9*8+0Ch]
0x1800236b8  cmp     r9d, 0FFFFFFFFh
0x1800236bc  jz      short loc_1800236CE
0x1800236be  mov     ecx, [r8+30h]
0x1800236c2  mov     rax, [r8+38h]
0x1800236c6  mov     [rax+rcx*4], r9d
0x1800236ca  inc     dword ptr [r8+30h]
0x1800236ce  inc     edx; unsigned int
0x1800236d0  cmp     edx, [rsi+58h]
0x1800236d3  jl      short loc_1800236A1
0x1800236d5  test    edi, edi
0x1800236d7  jns     short loc_1800236E6
0x1800236d9  mov     rcx, [r14]; this
0x1800236dc  test    rcx, rcx
0x1800236df  jz      short loc_1800236E6
0x1800236e1  call    ??_GCTableInfo@@QEAAPEAXI@Z; CTableInfo::`scalar deleting destructor'(uint)
0x1800236e6  mov     eax, edi
0x1800236e8  mov     rbx, [rsp+48h+arg_0]
0x1800236ed  mov     rbp, [rsp+48h+arg_18]
0x1800236f2  add     rsp, 20h
0x1800236f6  pop     r15
0x1800236f8  pop     r14
0x1800236fa  pop     r13
0x1800236fc  pop     rdi
0x1800236fd  pop     rsi
0x1800236fe  retn
```
