# CXMLReader::Fetch(CXMLRowset *,unsigned __int64)

- ea: `0x1800263a4`
- end: `0x1800266a4`
- name: `?Fetch@CXMLReader@@QEAAJPEAVCXMLRowset@@_K@Z`
- size: `768`
- prototype: `__int64 __fastcall(CXMLReader *__hidden this, struct CXMLRowset *, unsigned __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x180028550`
- `0x180029400`

## callees

- `0x18001b008`
- `0x1800263a4`
- `0x1800267cc`
- `0x180026a9c`
- `0x18002701c`
- `0x1800274b8`
- `0x180028550`
- `0x1800286bc`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall CXMLReader::Fetch(CXMLReader *this, struct CXMLRowset *a2, __int64 a3)
{
  struct CParseNode ***v3; // r15
  __int64 v4; // rax
  struct CParseNode ***v5; // rbx
  __int64 *v6; // r14
  struct CXMLRowset *v7; // r8
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // r13
  int Data; // ebx
  int v13; // eax
  __int64 v14; // r12
  struct CParseNode *v15; // rbp
  unsigned int v16; // edx
  unsigned int v17; // esi
  int v18; // eax
  struct CParseNode *v19; // r8
  __int64 v20; // rcx
  unsigned int v22; // [rsp+40h] [rbp-48h]
  unsigned int v25; // [rsp+A8h] [rbp+20h] BYREF

  v3 = (struct CParseNode ***)((char *)this + 424);
  v4 = a3;
  v5 = (struct CParseNode ***)((char *)this + 424);
  v6 = (__int64 *)((char *)this + 456);
  v7 = a2;
  while ( 2 )
  {
    if ( v4 )
    {
      v9 = *(_DWORD *)(v4 + 8);
      if ( v9 )
      {
        if ( v9 < *((_DWORD *)this + 108) )
        {
          v10 = *v6;
          v11 = v4;
          goto LABEL_18;
        }
        return 1;
      }
      v5 = v3;
    }
    v10 = *v6;
    if ( *v6 )
    {
      Data = 0;
      v13 = 2;
    }
    else
    {
      if ( *((_DWORD *)this + 108) )
        CXMLReader::ReduceStack(this, **v5);
      Data = (*(__int64 (__fastcall **)(_QWORD, __int64, struct CXMLRowset *))(**((_QWORD **)this + 56) + 192LL))(
               *((_QWORD *)this + 56),
               0xFFFFFFFFLL,
               v7);
      v13 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 56) + 200LL))(*((_QWORD *)this + 56));
      v10 = *v6;
      if ( !*v6 )
      {
LABEL_38:
        if ( v13 == 3 )
          goto LABEL_43;
        return 1;
      }
      if ( *(_DWORD *)v10 == 4 && v13 == 3 )
        return 1;
      v7 = a2;
    }
    if ( *(_DWORD *)v10 == 1 && *(struct CXMLRowset **)(v10 + 8) != v7 )
      goto LABEL_38;
    v9 = 0;
    v11 = 0;
LABEL_18:
    v14 = 0;
    v15 = (*v3)[v9];
    if ( (*((_BYTE *)v15 + 40) & 4) != 0 )
      v14 = *((_QWORD *)v15 + 2);
    if ( (unsigned int)(*(_DWORD *)v10 - 4) > 2 )
    {
      CXMLReader::PrepareData(this, v7);
      v16 = *((_DWORD *)v15 + 6);
      v17 = v9 + 1;
      v22 = v16;
      Data = 0;
      while ( 1 )
      {
        v25 = v17;
        if ( v17 >= v16 )
        {
          if ( v11 )
            *(_DWORD *)(v11 + 8) = v16;
          *v6 = 0;
LABEL_43:
          if ( Data < 0 )
          {
LABEL_49:
            if ( *((_DWORD *)this + 108) )
              CXMLReader::ReduceStack(this, **v3);
          }
          return (unsigned int)Data;
        }
        if ( v14 )
          break;
        v19 = (*v3)[v17];
        if ( *((struct CParseNode **)v19 + 2) == v15 && (unsigned int)(*((_DWORD *)v19 + 2) - 1) <= 1 )
        {
          Data = CXMLReader::GetData(this, a2, v19);
          if ( Data < 0 )
            goto LABEL_49;
LABEL_33:
          v16 = v22;
        }
LABEL_34:
        ++v17;
      }
      if ( *(_DWORD *)(*(_QWORD *)(v14 + 8LL * v17) + 4LL) != 2 )
        goto LABEL_34;
      v18 = CXMLReader::GetData(this, a2, (struct _XML_NODE_INFO **)(v14 + 8LL * v17), &v25, v16);
      Data = v18;
      if ( v18 < 0 )
        goto LABEL_49;
      if ( v18 == 1 )
      {
        v17 = v25;
        if ( (unsigned __int8)CXMLReader::IsMatch(
                                this,
                                *(_QWORD *)(*(_QWORD *)(v14 + 8LL * v25) + 16LL),
                                *(unsigned int *)(*(_QWORD *)(v14 + 8LL * v25) + 24LL),
                                *(unsigned int *)(*(_QWORD *)(v14 + 8LL * v25) + 28LL),
                                &wszDuplicate,
                                9,
                                3) )
        {
          v5 = v3;
          if ( (*((_BYTE *)v15 + 40) & 1) == 0 )
          {
            v20 = *((_QWORD *)this + 56);
            *((_QWORD *)this + 58) = v15;
            *((_BYTE *)this + 400) = 0;
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 192LL))(v20, 0xFFFFFFFFLL);
            *((_QWORD *)this + 58) = 0;
          }
          v7 = a2;
          v4 = a3;
          *v6 = 0;
          continue;
        }
        Data = 0;
      }
      else
      {
        v17 = v25;
      }
      goto LABEL_33;
    }
    break;
  }
  Data = CXMLReader::ProcessUpdate(this, v7);
  if ( Data < 0 )
  {
    if ( (bidGblFlags & 2) != 0 && off_180049D18[0] )
      bidTraceW(off_180049208[0], 1698816, off_180049D18[0], (unsigned int)Data, 1659);
    goto LABEL_49;
  }
  return (unsigned int)Data;
}

```

## disassembly

```asm
0x1800263a4  mov     [rsp+arg_0], rbx
0x1800263a9  mov     [rsp+arg_10], r8
0x1800263ae  mov     [rsp+arg_8], rdx
0x1800263b3  push    rbp
0x1800263b4  push    rsi
0x1800263b5  push    rdi
0x1800263b6  push    r12
0x1800263b8  push    r13
0x1800263ba  push    r14
0x1800263bc  push    r15
0x1800263be  sub     rsp, 50h
0x1800263c2  lea     r15, [rcx+1A8h]
0x1800263c9  mov     rax, r8
0x1800263cc  mov     rbx, r15
0x1800263cf  lea     r14, [rcx+1C8h]
0x1800263d6  mov     r8, rdx
0x1800263d9  mov     rdi, rcx
0x1800263dc  mov     esi, 1
0x1800263e1  test    rax, rax
0x1800263e4  jz      short loc_180026407
0x1800263e6  mov     ebx, [rax+8]
0x1800263e9  test    ebx, ebx
0x1800263eb  jz      short loc_180026404
0x1800263ed  cmp     ebx, [rdi+1B0h]
0x1800263f3  jnb     loc_180026615
0x1800263f9  mov     rdx, [r14]
0x1800263fc  mov     r13, rax
0x1800263ff  jmp     loc_180026492
0x180026404  mov     rbx, r15
0x180026407  mov     rdx, [r14]
0x18002640a  test    rdx, rdx
0x18002640d  jnz     short loc_18002647A
0x18002640f  cmp     [rdi+1B0h], edx
0x180026415  jz      short loc_180026425
0x180026417  mov     rdx, [rbx]
0x18002641a  mov     rcx, rdi; this
0x18002641d  mov     rdx, [rdx]; struct CParseNode *
0x180026420  call    ?ReduceStack@CXMLReader@@AEAAXPEAVCParseNode@@@Z; CXMLReader::ReduceStack(CParseNode *)
0x180026425  mov     rcx, [rdi+1C0h]
0x18002642c  or      edx, 0FFFFFFFFh
0x18002642f  mov     rax, [rcx]
0x180026432  mov     rax, [rax+0C0h]
0x180026439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002643e  mov     rcx, [rdi+1C0h]
0x180026445  mov     ebx, eax
0x180026447  mov     rdx, [rcx]
0x18002644a  mov     rax, [rdx+0C8h]
0x180026451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026456  mov     rdx, [r14]
0x180026459  test    rdx, rdx
0x18002645c  jz      loc_180026610
0x180026462  cmp     dword ptr [rdx], 4
0x180026465  jnz     short loc_180026470
0x180026467  cmp     eax, 3
0x18002646a  jz      loc_180026615
0x180026470  mov     r8, [rsp+88h+arg_8]
0x180026478  jmp     short loc_18002647F
0x18002647a  xor     ebx, ebx
0x18002647c  lea     eax, [rbx+2]
0x18002647f  cmp     [rdx], esi
0x180026481  jnz     short loc_18002648D
0x180026483  cmp     [rdx+8], r8
0x180026487  jnz     loc_180026610
0x18002648d  xor     ebx, ebx
0x18002648f  xor     r13d, r13d
0x180026492  mov     rax, [r15]
0x180026495  xor     r12d, r12d
0x180026498  mov     ecx, ebx
0x18002649a  mov     rbp, [rax+rcx*8]
0x18002649e  test    byte ptr [rbp+28h], 4
0x1800264a2  jz      short loc_1800264A8
0x1800264a4  mov     r12, [rbp+10h]
0x1800264a8  mov     eax, [rdx]
0x1800264aa  mov     rcx, rdi; this
0x1800264ad  sub     eax, 4
0x1800264b0  mov     rdx, r8; struct CXMLRowset *
0x1800264b3  cmp     eax, 2
0x1800264b6  jbe     loc_18002662F
0x1800264bc  call    ?PrepareData@CXMLReader@@AEAAXPEAVCXMLRowset@@@Z; CXMLReader::PrepareData(CXMLRowset *)
0x1800264c1  mov     edx, [rbp+18h]
0x1800264c4  lea     esi, [rbx+1]
0x1800264c7  mov     [rsp+88h+var_48], edx
0x1800264cb  xor     ebx, ebx
0x1800264cd  mov     ecx, esi
0x1800264cf  mov     [rsp+88h+arg_18], esi
0x1800264d6  mov     eax, esi
0x1800264d8  cmp     ecx, edx
0x1800264da  jnb     loc_180026619
0x1800264e0  mov     r8d, eax
0x1800264e3  test    r12, r12
0x1800264e6  jz      loc_180026577
0x1800264ec  mov     rax, [r12+r8*8]
0x1800264f0  cmp     dword ptr [rax+4], 2
0x1800264f4  jnz     loc_1800265AD
0x1800264fa  mov     eax, ecx
0x1800264fc  lea     r9, [rsp+88h+arg_18]; unsigned int *
0x180026504  mov     [rsp+88h+var_68], edx; unsigned int
0x180026508  mov     rcx, rdi; this
0x18002650b  mov     rdx, [rsp+88h+arg_8]; struct CXMLRowset *
0x180026513  lea     r8, [r12+rax*8]; struct _XML_NODE_INFO **
0x180026517  call    ?GetData@CXMLReader@@QEAAJPEAVCXMLRowset@@PEAPEAU_XML_NODE_INFO@@PEAKK@Z; CXMLReader::GetData(CXMLRowset *,_XML_NODE_INFO * *,ulong *,ulong)
0x18002651c  mov     ebx, eax
0x18002651e  test    eax, eax
0x180026520  js      loc_180026672
0x180026526  cmp     eax, 1
0x180026529  jnz     short loc_18002656E
0x18002652b  mov     esi, [rsp+88h+arg_18]
0x180026532  lea     rax, ?wszDuplicate@@3PAGA; "duplicate"
0x180026539  mov     [rsp+88h+var_58], 3
0x180026541  mov     rcx, rdi
0x180026544  mov     [rsp+88h+var_60], 9
0x18002654c  mov     qword ptr [rsp+88h+var_68], rax
0x180026551  mov     rdx, [r12+rsi*8]
0x180026555  mov     r9d, [rdx+1Ch]
0x180026559  mov     r8d, [rdx+18h]
0x18002655d  mov     rdx, [rdx+10h]
0x180026561  call    ?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z; CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)
0x180026566  test    al, al
0x180026568  jnz     short loc_1800265B4
0x18002656a  xor     ebx, ebx
0x18002656c  jmp     short loc_1800265A9
0x18002656e  mov     esi, [rsp+88h+arg_18]
0x180026575  jmp     short loc_1800265A9
0x180026577  mov     rax, [r15]
0x18002657a  mov     r8, [rax+r8*8]; struct CParseNode *
0x18002657e  cmp     [r8+10h], rbp
0x180026582  jnz     short loc_1800265AD
0x180026584  mov     eax, [r8+8]
0x180026588  dec     eax
0x18002658a  cmp     eax, 1
0x18002658d  ja      short loc_1800265AD
0x18002658f  mov     rdx, [rsp+88h+arg_8]; struct CXMLRowset *
0x180026597  mov     rcx, rdi; this
0x18002659a  call    ?GetData@CXMLReader@@QEAAJPEAVCXMLRowset@@PEAVCParseNode@@@Z; CXMLReader::GetData(CXMLRowset *,CParseNode *)
0x18002659f  mov     ebx, eax
0x1800265a1  test    eax, eax
0x1800265a3  js      loc_180026672
0x1800265a9  mov     edx, [rsp+88h+var_48]
0x1800265ad  inc     esi
0x1800265af  jmp     loc_1800264CD
0x1800265b4  mov     esi, 1
0x1800265b9  mov     rbx, r15
0x1800265bc  test    [rbp+28h], sil
0x1800265c0  jnz     short loc_1800265F4
0x1800265c2  mov     rcx, [rdi+1C0h]
0x1800265c9  or      edx, 0FFFFFFFFh
0x1800265cc  mov     [rdi+1D0h], rbp
0x1800265d3  mov     byte ptr [rdi+190h], 0
0x1800265da  mov     rax, [rcx]
0x1800265dd  mov     rax, [rax+0C0h]
0x1800265e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800265e9  mov     qword ptr [rdi+1D0h], 0
0x1800265f4  mov     r8, [rsp+88h+arg_8]
0x1800265fc  mov     rax, [rsp+88h+arg_10]
0x180026604  mov     qword ptr [r14], 0
0x18002660b  jmp     loc_1800263E1
0x180026610  cmp     eax, 3
0x180026613  jz      short loc_180026629
0x180026615  mov     ebx, esi
0x180026617  jmp     short loc_180026689
0x180026619  test    r13, r13
0x18002661c  jz      short loc_180026622
0x18002661e  mov     [r13+8], edx
0x180026622  mov     qword ptr [r14], 0
0x180026629  test    ebx, ebx
0x18002662b  jns     short loc_180026689
0x18002662d  jmp     short loc_180026672
0x18002662f  call    ?ProcessUpdate@CXMLReader@@AEAAJPEAVCXMLRowset@@W4SYMBOL_TYPE@@@Z; CXMLReader::ProcessUpdate(CXMLRowset *,SYMBOL_TYPE)
0x180026634  mov     ebx, eax
0x180026636  test    eax, eax
0x180026638  jns     short loc_180026689
0x18002663a  test    byte ptr cs:_bidGblFlags, 2
0x180026641  jz      short loc_180026672
0x180026643  mov     rax, cs:off_180049D18; "<CXMLReader::Fetch|ADO|ERR>  HRESULT: 0"...
0x18002664a  test    rax, rax
0x18002664d  jz      short loc_180026672
0x18002664f  mov     r8, cs:off_180049D18; "<CXMLReader::Fetch|ADO|ERR>  HRESULT: 0"...
0x180026656  mov     r9d, ebx
0x180026659  mov     rcx, cs:off_180049208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180026660  mov     edx, 19EC00h
0x180026665  mov     [rsp+88h+var_68], 67Bh
0x18002666d  call    _bidTraceW
0x180026672  cmp     dword ptr [rdi+1B0h], 0
0x180026679  jz      short loc_180026689
0x18002667b  mov     rdx, [r15]
0x18002667e  mov     rcx, rdi; this
0x180026681  mov     rdx, [rdx]; struct CParseNode *
0x180026684  call    ?ReduceStack@CXMLReader@@AEAAXPEAVCParseNode@@@Z; CXMLReader::ReduceStack(CParseNode *)
0x180026689  mov     eax, ebx
0x18002668b  mov     rbx, [rsp+88h+arg_0]
0x180026693  add     rsp, 50h
0x180026697  pop     r15
0x180026699  pop     r14
0x18002669b  pop     r13
0x18002669d  pop     r12
0x18002669f  pop     rdi
0x1800266a0  pop     rsi
0x1800266a1  pop     rbp
0x1800266a2  retn
```
