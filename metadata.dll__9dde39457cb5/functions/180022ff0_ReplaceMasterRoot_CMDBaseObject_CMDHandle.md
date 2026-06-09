# ReplaceMasterRoot(CMDBaseObject *,CMDHandle *)

- ea: `0x180022ff0`
- end: `0x1800231e6`
- name: `?ReplaceMasterRoot@@YAJPEAVCMDBaseObject@@PEAVCMDHandle@@@Z`
- size: `502`
- prototype: `__int64 __fastcall(struct CMDBaseObject *, struct CMDHandle *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18001c580`

## callees

- `0x18000363c`
- `0x180003678`
- `0x1800053f0`
- `0x180007574`
- `0x180007810`
- `0x1800147a4`
- `0x1800154b8`
- `0x18001558c`
- `0x18001ca3c`
- `0x180022ff0`
- `0x180031010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180023135`
- `msvcrt!_wcsicmp` at `0x180023135`

## pseudocode

```c
__int64 __fastcall ReplaceMasterRoot(struct CMDBaseObject *a1, struct CMDHandle *a2)
{
  int v4; // r14d
  void **MainDataBuffer; // rax
  void **v6; // rsi
  __int64 result; // rax
  unsigned int AllDataObjects; // ebp
  int v9; // r8d
  unsigned int i; // edi
  char *v11; // rdx
  void **v12; // rcx
  _QWORD *v13; // rax
  _QWORD *v14; // rcx
  struct CMDBaseData *v15; // rdx
  unsigned int v16; // ebx
  unsigned int v17; // edi
  unsigned int j; // edx
  const wchar_t *Name; // rax
  CMDBaseObject *v20; // rax
  struct CMDBaseObject *v21; // r11
  struct CMDBaseObject *v22; // rbx
  int v23; // [rsp+80h] [rbp+18h] BYREF

  v4 = 0;
  MainDataBuffer = GetMainDataBuffer(0);
  v6 = MainDataBuffer;
  if ( !MainDataBuffer )
    return 2147942414LL;
  AllDataObjects = CMDBaseObject::GetAllDataObjects(g_pboMasterRoot, MainDataBuffer, 0, 0, 0, 0, 0, 0);
  for ( i = 0; i < AllDataObjects; ++i )
  {
    v11 = (char *)*v6;
    if ( i == *((_DWORD *)*v6 + 24) + 1 && (v12 = (void **)*((_QWORD *)v11 + 13)) != 0 )
    {
      if ( *v12 == v11 + 80 )
        goto LABEL_15;
      *((_DWORD *)v11 + 24) = i;
      v13 = *v12;
    }
    else
    {
      *((_DWORD *)v11 + 24) = i;
      v14 = v11 + 80;
      v13 = (_QWORD *)*((_QWORD *)v11 + 10);
      v9 = i;
      if ( i )
      {
        while ( v13 != v14 )
        {
          v13 = (_QWORD *)*v13;
          if ( !--v9 )
            goto LABEL_12;
        }
LABEL_15:
        *((_QWORD *)v11 + 13) = 0;
        *((_DWORD *)v11 + 24) = 0;
        return 2147500037LL;
      }
LABEL_12:
      if ( v13 == v14 )
        goto LABEL_15;
    }
    *((_QWORD *)v11 + 13) = v13;
    v15 = (struct CMDBaseData *)*(v13 - 2);
    if ( !v15 )
      return 2147500037LL;
    v16 = *((_DWORD *)v15 + 2);
    CMDBaseObject::RemoveDataObject(g_pboMasterRoot, v15, v9, 1);
    CMDHandle::SetChangeData(a2, g_pboMasterRoot, 8u, v16, 0);
  }
  v17 = 0;
  if ( AllDataObjects )
    v4 = 1;
  v23 = v4;
  FreeMainDataBuffer(v6);
  for ( j = 0; ; j = v17 )
  {
    v20 = CMDBaseObject::EnumChildObject(g_pboMasterRoot, j);
    v22 = v20;
    if ( !v20 )
      break;
    Name = (const wchar_t *)CMDBaseObject::GetName(v20, 1, 0);
    if ( _wcsicmp(L"SCHEMA", Name) )
    {
      v23 = 1;
      CMDBaseObject::RemoveChildObject(g_pboMasterRoot, v22);
      if ( CMDHandle::SetChangeData(a2, v22, 1u, 0, 0) && v22 )
        (**(void (__fastcall ***)(struct CMDBaseObject *, __int64))v22)(v22, 1);
    }
    else
    {
      ++v17;
    }
  }
  result = CopyTree(a2, v21, a1, &v23);
  if ( v23 )
    ++*(_DWORD *)&g_dwSystemChangeNumber;
  return result;
}

```

## disassembly

```asm
0x180022ff0  mov     [rsp+arg_0], rbx
0x180022ff5  mov     [rsp+arg_8], rbp
0x180022ffa  push    rsi
0x180022ffb  push    rdi
0x180022ffc  push    r12
0x180022ffe  push    r14
0x180023000  push    r15
0x180023002  sub     rsp, 40h
0x180023006  mov     r12, rcx
0x180023009  mov     r15, rdx
0x18002300c  xor     ecx, ecx; int
0x18002300e  xor     r14d, r14d
0x180023011  call    ?GetMainDataBuffer@@YAPEAPEAXH@Z; GetMainDataBuffer(int)
0x180023016  mov     rsi, rax
0x180023019  test    rax, rax
0x18002301c  jnz     short loc_180023028
0x18002301e  mov     eax, 8007000Eh
0x180023023  jmp     loc_1800231CF
0x180023028  mov     rcx, cs:?g_pboMasterRoot@@3PEAVCMDBaseObject@@EA; this
0x18002302f  xor     r9d, r9d; unsigned int
0x180023032  mov     [rsp+68h+var_30], r14; unsigned int *
0x180023037  xor     r8d, r8d; unsigned int
0x18002303a  mov     [rsp+68h+var_38], r14d; int
0x18002303f  mov     rdx, rsi; void **
0x180023042  mov     [rsp+68h+var_40], r14d; int
0x180023047  mov     dword ptr [rsp+68h+var_48], r14d; unsigned int
0x18002304c  call    ?GetAllDataObjects@CMDBaseObject@@QEAAKPEAPEAXKKKHHPEAK@Z; CMDBaseObject::GetAllDataObjects(void * *,ulong,ulong,ulong,int,int,ulong *)
0x180023051  mov     ebp, eax
0x180023053  xor     edi, edi
0x180023055  cmp     edi, ebp
0x180023057  jnb     loc_1800230FF
0x18002305d  mov     rdx, [rsi]
0x180023060  mov     ecx, [rdx+60h]
0x180023063  inc     ecx
0x180023065  cmp     edi, ecx
0x180023067  jnz     short loc_180023083
0x180023069  mov     rcx, [rdx+68h]
0x18002306d  test    rcx, rcx
0x180023070  jz      short loc_180023083
0x180023072  lea     rax, [rdx+50h]
0x180023076  cmp     [rcx], rax
0x180023079  jz      short loc_1800230ED
0x18002307b  mov     [rdx+60h], edi
0x18002307e  mov     rax, [rcx]
0x180023081  jmp     short loc_1800230A7
0x180023083  mov     [rdx+60h], edi
0x180023086  lea     rcx, [rdx+50h]
0x18002308a  mov     rax, [rcx]
0x18002308d  mov     r8d, edi
0x180023090  test    edi, edi
0x180023092  jz      short loc_1800230A2
0x180023094  cmp     rax, rcx
0x180023097  jz      short loc_1800230ED
0x180023099  mov     rax, [rax]
0x18002309c  add     r8d, 0FFFFFFFFh; int
0x1800230a0  jnz     short loc_180023094
0x1800230a2  cmp     rax, rcx
0x1800230a5  jz      short loc_1800230ED
0x1800230a7  mov     [rdx+68h], rax
0x1800230ab  mov     rdx, [rax-10h]; struct CMDBaseData *
0x1800230af  test    rdx, rdx
0x1800230b2  jz      short loc_1800230F5
0x1800230b4  mov     rcx, cs:?g_pboMasterRoot@@3PEAVCMDBaseObject@@EA; this
0x1800230bb  mov     r9d, 1; int
0x1800230c1  mov     ebx, [rdx+8]
0x1800230c4  call    ?RemoveDataObject@CMDBaseObject@@QEAAJPEAVCMDBaseData@@HH@Z; CMDBaseObject::RemoveDataObject(CMDBaseData *,int,int)
0x1800230c9  mov     rdx, cs:?g_pboMasterRoot@@3PEAVCMDBaseObject@@EA; struct CMDBaseObject *
0x1800230d0  mov     r9d, ebx; unsigned int
0x1800230d3  mov     r8d, 8; unsigned int
0x1800230d9  mov     [rsp+68h+var_48], r14; unsigned __int16 *
0x1800230de  mov     rcx, r15; this
0x1800230e1  call    ?SetChangeData@CMDHandle@@QEAAJPEAVCMDBaseObject@@KKPEAG@Z; CMDHandle::SetChangeData(CMDBaseObject *,ulong,ulong,ushort *)
0x1800230e6  inc     edi
0x1800230e8  jmp     loc_180023055
0x1800230ed  mov     [rdx+68h], r14
0x1800230f1  mov     [rdx+60h], r14d
0x1800230f5  mov     eax, 80004005h
0x1800230fa  jmp     loc_1800231CF
0x1800230ff  xor     edi, edi
0x180023101  mov     rcx, rsi; Block
0x180023104  test    ebp, ebp
0x180023106  lea     ebp, [rdi+1]
0x180023109  cmovnz  r14d, ebp
0x18002310d  mov     [rsp+68h+arg_10], r14d
0x180023115  call    ?FreeMainDataBuffer@@YAXPEAPEAX@Z; FreeMainDataBuffer(void * *)
0x18002311a  xor     edx, edx
0x18002311c  jmp     short loc_18002318E
0x18002311e  xor     r8d, r8d; unsigned int *
0x180023121  mov     edx, ebp; int
0x180023123  mov     rcx, rbx; this
0x180023126  call    ?GetName@CMDBaseObject@@QEAAPEADHPEAK@Z; CMDBaseObject::GetName(int,ulong *)
0x18002312b  mov     rdx, rax; String2
0x18002312e  lea     rcx, aSchema_1; "SCHEMA"
0x180023135  call    cs:__imp__wcsicmp
0x18002313b  test    eax, eax
0x18002313d  jnz     short loc_180023143
0x18002313f  add     edi, ebp
0x180023141  jmp     short loc_18002318C
0x180023143  mov     rcx, cs:?g_pboMasterRoot@@3PEAVCMDBaseObject@@EA; this
0x18002314a  mov     rdx, rbx; struct CMDBaseObject *
0x18002314d  mov     [rsp+68h+arg_10], ebp
0x180023154  call    ?RemoveChildObject@CMDBaseObject@@QEAAJPEAV1@@Z; CMDBaseObject::RemoveChildObject(CMDBaseObject *)
0x180023159  xor     r9d, r9d; unsigned int
0x18002315c  mov     [rsp+68h+var_48], 0; unsigned __int16 *
0x180023165  mov     r8d, ebp; unsigned int
0x180023168  mov     rdx, rbx; struct CMDBaseObject *
0x18002316b  mov     rcx, r15; this
0x18002316e  call    ?SetChangeData@CMDHandle@@QEAAJPEAVCMDBaseObject@@KKPEAG@Z; CMDHandle::SetChangeData(CMDBaseObject *,ulong,ulong,ushort *)
0x180023173  test    eax, eax
0x180023175  jz      short loc_18002318C
0x180023177  test    rbx, rbx
0x18002317a  jz      short loc_18002318C
0x18002317c  mov     rax, [rbx]
0x18002317f  mov     edx, ebp
0x180023181  mov     rcx, rbx
0x180023184  mov     rax, [rax]
0x180023187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002318c  mov     edx, edi; unsigned int
0x18002318e  mov     r11, cs:?g_pboMasterRoot@@3PEAVCMDBaseObject@@EA; CMDBaseObject * g_pboMasterRoot
0x180023195  mov     rcx, r11; this
0x180023198  call    ?EnumChildObject@CMDBaseObject@@QEAAPEAV1@K@Z; CMDBaseObject::EnumChildObject(ulong)
0x18002319d  mov     rbx, rax
0x1800231a0  test    rax, rax
0x1800231a3  jnz     loc_18002311E
0x1800231a9  lea     r9, [rsp+68h+arg_10]; int *
0x1800231b1  mov     r8, r12; struct CMDBaseObject *
0x1800231b4  mov     rdx, r11; struct CMDBaseObject *
0x1800231b7  mov     rcx, r15; struct CMDHandle *
0x1800231ba  call    ?CopyTree@@YAJPEAVCMDHandle@@PEAVCMDBaseObject@@1AEAH@Z; CopyTree(CMDHandle *,CMDBaseObject *,CMDBaseObject *,int &)
0x1800231bf  cmp     [rsp+68h+arg_10], 0
0x1800231c7  jz      short loc_1800231CF
0x1800231c9  add     cs:?g_dwSystemChangeNumber@@3KA, ebp; ulong g_dwSystemChangeNumber
0x1800231cf  mov     rbx, [rsp+68h+arg_0]
0x1800231d4  mov     rbp, [rsp+68h+arg_8]
0x1800231d9  add     rsp, 40h
0x1800231dd  pop     r15
0x1800231df  pop     r14
0x1800231e1  pop     r12
0x1800231e3  pop     rdi
0x1800231e4  pop     rsi
0x1800231e5  retn
```
