# CCommand::FInit(CRowsetProperties *)

- ea: `0x10013f50`
- end: `0x10014329`
- name: `?FInit@CCommand@@QAEJPAVCRowsetProperties@@@Z`
- size: `985`
- prototype: `int __thiscall(CCommand *__hidden this, struct CRowsetProperties *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10017160`

## callees

- `0x1000bcf0`
- `0x1000bea0`
- `0x10013f50`
- `0x10020410`
- `0x100204c0`
- `0x100215b0`
- `0x1004ce5d`
- `0x1004cea1`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x10013f93`
- `KERNEL32!InitializeCriticalSection` at `0x10013f93`

## pseudocode

```c
int __thiscall CCommand::FInit(CCommand *this, struct CRowsetProperties *a2)
{
  struct _RTL_CRITICAL_SECTION *v3; // edi
  void *RecursionCount; // ebx
  unsigned int *v5; // edi
  _DWORD *v6; // eax
  _DWORD *v7; // eax
  _DWORD *v8; // eax
  _DWORD *v9; // eax
  _DWORD *v10; // edx
  CCommand *v11; // ecx
  CCommand *v12; // eax
  _DWORD *v13; // eax
  _DWORD *v14; // edx
  _DWORD *v15; // ecx
  _DWORD *v16; // edx
  CCommand *v17; // ecx
  CCommand *v18; // eax
  _DWORD *v19; // eax
  bool v20; // zf
  int v21; // ecx
  int v22; // edi
  int v23; // eax
  _DWORD *v24; // ecx
  int v25; // eax
  int v26; // eax
  int result; // eax
  void *v28; // ebx
  _DWORD *v29; // eax
  _DWORD *v30; // ebx
  _DWORD *v31; // eax
  _DWORD *v32; // eax
  _DWORD *v33; // eax
  _DWORD *v34; // eax
  _DWORD *v35; // eax
  _DWORD *v36; // eax
  void *v37; // [esp-4h] [ebp-14h]
  void *v38; // [esp-4h] [ebp-14h]
  void *v39; // [esp-4h] [ebp-14h]
  void *v40; // [esp-4h] [ebp-14h]
  void *v41; // [esp-4h] [ebp-14h]
  void *v42; // [esp-4h] [ebp-14h]
  void *v43; // [esp-4h] [ebp-14h]
  CImpIAccessor *v44; // [esp+0h] [ebp-10h]
  int v45; // [esp+4h] [ebp-Ch]

  v3 = (struct _RTL_CRITICAL_SECTION *)operator new(0x30u);
  if ( v3 )
  {
    RecursionCount = (void *)*((_DWORD *)this + 2);
    v3->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CImpIAccessor::`vftable';
    v3->LockCount = 0;
    v3->RecursionCount = (LONG)this;
    v3->LockSemaphore = 0;
    v3->SpinCount = 0;
    InitializeCriticalSection(v3 + 1);
    if ( !RecursionCount )
      RecursionCount = (void *)v3->RecursionCount;
    v3->OwningThread = RecursionCount;
    *((_DWORD *)this + 3) = v3;
    if ( v3 )
    {
      if ( CImpIAccessor::FInit(v44, v45) >= 0 )
        goto LABEL_10;
      v5 = (unsigned int *)*((_DWORD *)this + 3);
      if ( v5 )
      {
        CImpIAccessor::~CImpIAccessor(*((struct _RTL_CRITICAL_SECTION **)this + 3), v5, (unsigned int)this);
        operator delete(v5);
      }
    }
  }
  else
  {
    *((_DWORD *)this + 3) = 0;
  }
  *((_DWORD *)this + 3) = 0;
LABEL_10:
  v6 = operator new(0xCu);
  if ( v6 )
  {
    *v6 = &CImpICommandText::`vftable';
    v6[1] = 0;
    v6[2] = this;
  }
  else
  {
    v6 = 0;
  }
  *((_DWORD *)this + 4) = v6;
  v7 = operator new(0x20u);
  if ( v7 )
  {
    *v7 = &CImpICommandProperties::`vftable';
    v7[4] = 0;
    v7[5] = 0;
    v7[6] = 0;
    v7[3] = &CRowsetProperties::`vftable';
    v7[7] = 0;
    v7[1] = 0;
    v7[2] = this;
  }
  else
  {
    v7 = 0;
  }
  *((_DWORD *)this + 5) = v7;
  v8 = operator new(0xCu);
  if ( v8 )
  {
    *v8 = &CImpICommandPrepare::`vftable';
    v8[1] = 0;
    v8[2] = this;
  }
  else
  {
    v8 = 0;
  }
  *((_DWORD *)this + 6) = v8;
  v9 = operator new(0xCu);
  if ( v9 )
  {
    *v9 = &CImpICommandWithParameters::`vftable';
    v9[1] = 0;
    v9[2] = this;
  }
  else
  {
    v9 = 0;
  }
  *((_DWORD *)this + 7) = v9;
  v10 = operator new(0x14u);
  if ( v10 )
  {
    v11 = (CCommand *)*((_DWORD *)this + 2);
    v12 = this;
    *v10 = &CImpIColumnsInfo::`vftable';
    v10[1] = 0;
    if ( v11 )
      v12 = v11;
    v10[2] = this;
    v10[4] = 0;
    v10[3] = v12;
  }
  else
  {
    v10 = 0;
  }
  *((_DWORD *)this + 8) = v10;
  v13 = operator new(0x14u);
  v14 = v13;
  if ( v13 )
  {
    v15 = (_DWORD *)*((_DWORD *)this + 2);
    *v13 = &CImpIColumnsRowset::`vftable';
    if ( v15 )
      v13 = v15;
    v14[1] = 0;
    v14[2] = this;
    v14[3] = 0;
    v14[4] = v13;
  }
  else
  {
    v14 = 0;
  }
  *((_DWORD *)this + 9) = v14;
  v16 = operator new(0x14u);
  if ( v16 )
  {
    v17 = (CCommand *)*((_DWORD *)this + 2);
    v18 = this;
    *v16 = &CImpIConvertType::`vftable';
    v16[1] = 0;
    if ( v17 )
      v18 = v17;
    v16[2] = this;
    v16[3] = 0;
    v16[4] = v18;
  }
  else
  {
    v16 = 0;
  }
  *((_DWORD *)this + 10) = v16;
  v19 = operator new(0xCu);
  if ( v19 )
  {
    *v19 = &CImpICommandPersist::`vftable';
    v19[1] = 0;
    v19[2] = this;
  }
  else
  {
    v19 = 0;
  }
  v20 = *((_DWORD *)this + 3) == 0;
  *((_DWORD *)this + 11) = v19;
  if ( !v20
    && *((_DWORD *)this + 4)
    && (v21 = *((_DWORD *)this + 5)) != 0
    && *((_DWORD *)this + 6)
    && *((_DWORD *)this + 7)
    && *((_DWORD *)this + 8)
    && *((_DWORD *)this + 9)
    && *((_DWORD *)this + 10)
    && v19 )
  {
    v22 = CSettableProperties::FInit((CSettableProperties *)(v21 + 12));
    if ( v22 >= 0 )
    {
      v23 = CRowsetProperties::CopyPropertiesFromStaticTable(
              (CRowsetProperties *)(*((_DWORD *)this + 5) + 12),
              (const struct DBInfoProps *)&rgDBInfoProps);
      v24 = (_DWORD *)*((_DWORD *)this + 5);
      v22 = v23;
      v25 = v24[5];
      v24[4] = 1;
      *(_DWORD *)(v25 + 36) = 1;
      v26 = v24[6];
      if ( v26 )
        *(_DWORD *)(v26 + 36) = 1;
      if ( v22 >= 0 )
        return v22;
    }
  }
  else
  {
    v22 = -2147024882;
  }
  v28 = (void *)*((_DWORD *)this + 3);
  if ( v28 )
  {
    CImpIAccessor::~CImpIAccessor(*((struct _RTL_CRITICAL_SECTION **)this + 3), (unsigned int *)v22, (unsigned int)this);
    operator delete(v28);
  }
  v29 = (_DWORD *)*((_DWORD *)this + 4);
  if ( v29 )
  {
    v37 = (void *)*((_DWORD *)this + 4);
    *v29 = &CImpICommandText::`vftable';
    operator delete(v37);
  }
  v30 = (_DWORD *)*((_DWORD *)this + 5);
  if ( v30 )
  {
    *v30 = &CImpICommandProperties::`vftable';
    CSettableProperties::~CSettableProperties((CSettableProperties *)(v30 + 3));
    operator delete(v30);
  }
  v31 = (_DWORD *)*((_DWORD *)this + 6);
  if ( v31 )
  {
    v38 = (void *)*((_DWORD *)this + 6);
    *v31 = &CImpICommandPrepare::`vftable';
    operator delete(v38);
  }
  v32 = (_DWORD *)*((_DWORD *)this + 7);
  if ( v32 )
  {
    v39 = (void *)*((_DWORD *)this + 7);
    *v32 = &CImpICommandWithParameters::`vftable';
    operator delete(v39);
  }
  v33 = (_DWORD *)*((_DWORD *)this + 8);
  if ( v33 )
  {
    v40 = (void *)*((_DWORD *)this + 8);
    *v33 = &CImpIColumnsInfo::`vftable';
    operator delete(v40);
  }
  v34 = (_DWORD *)*((_DWORD *)this + 9);
  if ( v34 )
  {
    v41 = (void *)*((_DWORD *)this + 9);
    *v34 = &CImpIColumnsRowset::`vftable';
    operator delete(v41);
  }
  v35 = (_DWORD *)*((_DWORD *)this + 10);
  if ( v35 )
  {
    v42 = (void *)*((_DWORD *)this + 10);
    *v35 = &CImpIConvertType::`vftable';
    operator delete(v42);
  }
  v36 = (_DWORD *)*((_DWORD *)this + 11);
  if ( v36 )
  {
    v43 = (void *)*((_DWORD *)this + 11);
    *v36 = &CImpICommandPersist::`vftable';
    operator delete(v43);
  }
  result = v22;
  *((_DWORD *)this + 3) = 0;
  *((_DWORD *)this + 4) = 0;
  *((_DWORD *)this + 5) = 0;
  *((_DWORD *)this + 6) = 0;
  *((_DWORD *)this + 7) = 0;
  *((_DWORD *)this + 8) = 0;
  *((_DWORD *)this + 9) = 0;
  *((_DWORD *)this + 10) = 0;
  *((_DWORD *)this + 11) = 0;
  return result;
}

```

## disassembly

```asm
0x10013f50  mov     edi, edi
0x10013f52  push    ebp
0x10013f53  mov     ebp, esp
0x10013f55  push    ecx
0x10013f56  push    ebx
0x10013f57  push    esi; int
0x10013f58  push    edi; this
0x10013f59  push    30h ; '0'; Size
0x10013f5b  mov     esi, ecx
0x10013f5d  call    ??2@YAPAXI@Z; operator new(uint)
0x10013f62  mov     edi, eax
0x10013f64  add     esp, 4
0x10013f67  mov     [ebp+var_4], edi
0x10013f6a  test    edi, edi
0x10013f6c  jz      short loc_10013FD0
0x10013f6e  mov     ebx, [esi+8]
0x10013f71  lea     eax, [edi+18h]
0x10013f74  push    eax; lpCriticalSection
0x10013f75  mov     dword ptr [edi], offset ??_7CImpIAccessor@@6B@; const CImpIAccessor::`vftable'
0x10013f7b  mov     dword ptr [edi+4], 0
0x10013f82  mov     [edi+8], esi
0x10013f85  mov     dword ptr [edi+10h], 0
0x10013f8c  mov     dword ptr [edi+14h], 0
0x10013f93  call    ds:__imp__InitializeCriticalSection@4; InitializeCriticalSection(x)
0x10013f99  test    ebx, ebx
0x10013f9b  jnz     short loc_10013FA0
0x10013f9d  mov     ebx, [edi+8]
0x10013fa0  mov     [edi+0Ch], ebx
0x10013fa3  mov     [esi+0Ch], edi
0x10013fa6  test    edi, edi
0x10013fa8  jz      short loc_10013FD7
0x10013faa  xor     edx, edx
0x10013fac  mov     ecx, edi
0x10013fae  call    ?FInit@CImpIAccessor@@QAGJH@Z; CImpIAccessor::FInit(int)
0x10013fb3  test    eax, eax
0x10013fb5  jns     short loc_10013FDE
0x10013fb7  mov     edi, [esi+0Ch]
0x10013fba  test    edi, edi
0x10013fbc  jz      short loc_10013FD7
0x10013fbe  mov     ecx, edi; this
0x10013fc0  call    ??1CImpIAccessor@@QAE@XZ; CImpIAccessor::~CImpIAccessor(void)
0x10013fc5  push    edi; Block
0x10013fc6  call    ??3@YAXPAX@Z; operator delete(void *)
0x10013fcb  add     esp, 4
0x10013fce  jmp     short loc_10013FD7
0x10013fd0  mov     dword ptr [esi+0Ch], 0
0x10013fd7  mov     dword ptr [esi+0Ch], 0
0x10013fde  push    0Ch; Size
0x10013fe0  call    ??2@YAPAXI@Z; operator new(uint)
0x10013fe5  add     esp, 4
0x10013fe8  mov     [ebp+var_4], eax
0x10013feb  test    eax, eax
0x10013fed  jz      short loc_10014001
0x10013fef  mov     dword ptr [eax], offset ??_7CImpICommandText@@6B@; const CImpICommandText::`vftable'
0x10013ff5  mov     dword ptr [eax+4], 0
0x10013ffc  mov     [eax+8], esi
0x10013fff  jmp     short loc_10014003
0x10014001  xor     eax, eax
0x10014003  push    20h ; ' '; Size
0x10014005  mov     [esi+10h], eax
0x10014008  call    ??2@YAPAXI@Z; operator new(uint)
0x1001400d  add     esp, 4
0x10014010  mov     [ebp+var_4], eax
0x10014013  test    eax, eax
0x10014015  jz      short loc_1001404C
0x10014017  mov     dword ptr [eax], offset ??_7CImpICommandProperties@@6B@; const CImpICommandProperties::`vftable'
0x1001401d  mov     dword ptr [eax+10h], 0
0x10014024  mov     dword ptr [eax+14h], 0
0x1001402b  mov     dword ptr [eax+18h], 0
0x10014032  mov     dword ptr [eax+0Ch], offset ??_7CRowsetProperties@@6B@; const CRowsetProperties::`vftable'
0x10014039  mov     dword ptr [eax+1Ch], 0
0x10014040  mov     dword ptr [eax+4], 0
0x10014047  mov     [eax+8], esi
0x1001404a  jmp     short loc_1001404E
0x1001404c  xor     eax, eax
0x1001404e  push    0Ch; Size
0x10014050  mov     [esi+14h], eax
0x10014053  call    ??2@YAPAXI@Z; operator new(uint)
0x10014058  add     esp, 4
0x1001405b  mov     [ebp+var_4], eax
0x1001405e  test    eax, eax
0x10014060  jz      short loc_10014074
0x10014062  mov     dword ptr [eax], offset ??_7CImpICommandPrepare@@6B@; const CImpICommandPrepare::`vftable'
0x10014068  mov     dword ptr [eax+4], 0
0x1001406f  mov     [eax+8], esi
0x10014072  jmp     short loc_10014076
0x10014074  xor     eax, eax
0x10014076  push    0Ch; Size
0x10014078  mov     [esi+18h], eax
0x1001407b  call    ??2@YAPAXI@Z; operator new(uint)
0x10014080  add     esp, 4
0x10014083  mov     [ebp+var_4], eax
0x10014086  test    eax, eax
0x10014088  jz      short loc_1001409C
0x1001408a  mov     dword ptr [eax], offset ??_7CImpICommandWithParameters@@6B@; const CImpICommandWithParameters::`vftable'
0x10014090  mov     dword ptr [eax+4], 0
0x10014097  mov     [eax+8], esi
0x1001409a  jmp     short loc_1001409E
0x1001409c  xor     eax, eax
0x1001409e  push    14h; Size
0x100140a0  mov     [esi+1Ch], eax
0x100140a3  call    ??2@YAPAXI@Z; operator new(uint)
0x100140a8  mov     edx, eax
0x100140aa  add     esp, 4
0x100140ad  mov     [ebp+var_4], edx
0x100140b0  test    edx, edx
0x100140b2  jz      short loc_100140DA
0x100140b4  mov     ecx, [esi+8]
0x100140b7  mov     eax, esi
0x100140b9  test    ecx, ecx
0x100140bb  mov     dword ptr [edx], offset ??_7CImpIColumnsInfo@@6B@; const CImpIColumnsInfo::`vftable'
0x100140c1  mov     dword ptr [edx+4], 0
0x100140c8  cmovnz  eax, ecx
0x100140cb  mov     [edx+8], esi
0x100140ce  mov     dword ptr [edx+10h], 0
0x100140d5  mov     [edx+0Ch], eax
0x100140d8  jmp     short loc_100140DC
0x100140da  xor     edx, edx
0x100140dc  push    14h; Size
0x100140de  mov     [esi+20h], edx
0x100140e1  call    ??2@YAPAXI@Z; operator new(uint)
0x100140e6  mov     edx, eax
0x100140e8  add     esp, 4
0x100140eb  mov     [ebp+var_4], edx
0x100140ee  test    edx, edx
0x100140f0  jz      short loc_10014116
0x100140f2  mov     ecx, [esi+8]
0x100140f5  test    ecx, ecx
0x100140f7  mov     dword ptr [edx], offset ??_7CImpIColumnsRowset@@6B@; const CImpIColumnsRowset::`vftable'
0x100140fd  cmovnz  eax, ecx
0x10014100  mov     dword ptr [edx+4], 0
0x10014107  mov     [edx+8], esi
0x1001410a  mov     dword ptr [edx+0Ch], 0
0x10014111  mov     [edx+10h], eax
0x10014114  jmp     short loc_10014118
0x10014116  xor     edx, edx
0x10014118  push    14h; Size
0x1001411a  mov     [esi+24h], edx
0x1001411d  call    ??2@YAPAXI@Z; operator new(uint)
0x10014122  mov     edx, eax
0x10014124  add     esp, 4
0x10014127  mov     [ebp+var_4], edx
0x1001412a  test    edx, edx
0x1001412c  jz      short loc_10014154
0x1001412e  mov     ecx, [esi+8]
0x10014131  mov     eax, esi
0x10014133  test    ecx, ecx
0x10014135  mov     dword ptr [edx], offset ??_7CImpIConvertType@@6B@; const CImpIConvertType::`vftable'
0x1001413b  mov     dword ptr [edx+4], 0
0x10014142  cmovnz  eax, ecx
0x10014145  mov     [edx+8], esi
0x10014148  mov     dword ptr [edx+0Ch], 0
0x1001414f  mov     [edx+10h], eax
0x10014152  jmp     short loc_10014156
0x10014154  xor     edx, edx
0x10014156  push    0Ch; Size
0x10014158  mov     [esi+28h], edx
0x1001415b  call    ??2@YAPAXI@Z; operator new(uint)
0x10014160  add     esp, 4
0x10014163  mov     [ebp+var_4], eax
0x10014166  test    eax, eax
0x10014168  jz      short loc_1001417C
0x1001416a  mov     dword ptr [eax], offset ??_7CImpICommandPersist@@6B@; const CImpICommandPersist::`vftable'
0x10014170  mov     dword ptr [eax+4], 0
0x10014177  mov     [eax+8], esi
0x1001417a  jmp     short loc_1001417E
0x1001417c  xor     eax, eax
0x1001417e  cmp     dword ptr [esi+0Ch], 0
0x10014182  mov     [esi+2Ch], eax
0x10014185  jz      loc_1001420B
0x1001418b  cmp     dword ptr [esi+10h], 0
0x1001418f  jz      short loc_1001420B
0x10014191  mov     ecx, [esi+14h]
0x10014194  test    ecx, ecx
0x10014196  jz      short loc_1001420B
0x10014198  cmp     dword ptr [esi+18h], 0
0x1001419c  jz      short loc_1001420B
0x1001419e  cmp     dword ptr [esi+1Ch], 0
0x100141a2  jz      short loc_1001420B
0x100141a4  cmp     dword ptr [esi+20h], 0
0x100141a8  jz      short loc_1001420B
0x100141aa  cmp     dword ptr [esi+24h], 0
0x100141ae  jz      short loc_1001420B
0x100141b0  cmp     dword ptr [esi+28h], 0
0x100141b4  jz      short loc_1001420B
0x100141b6  test    eax, eax
0x100141b8  jz      short loc_1001420B
0x100141ba  add     ecx, 0Ch; this
0x100141bd  call    ?FInit@CSettableProperties@@QAEJXZ; CSettableProperties::FInit(void)
0x100141c2  mov     edi, eax
0x100141c4  test    edi, edi
0x100141c6  js      short loc_10014210
0x100141c8  mov     ecx, [esi+14h]
0x100141cb  push    offset ?rgDBInfoProps@@3QBUDBInfoProps@@B; struct DBInfoProps *
0x100141d0  lea     ecx, [ecx+0Ch]; this
0x100141d3  call    ?CopyPropertiesFromStaticTable@CRowsetProperties@@QAEJPBUDBInfoProps@@@Z; CRowsetProperties::CopyPropertiesFromStaticTable(DBInfoProps const *)
0x100141d8  mov     ecx, [esi+14h]
0x100141db  mov     edi, eax
0x100141dd  mov     eax, [ecx+14h]
0x100141e0  mov     dword ptr [ecx+10h], 1
0x100141e7  mov     dword ptr [eax+24h], 1
0x100141ee  mov     eax, [ecx+18h]
0x100141f1  test    eax, eax
0x100141f3  jz      short loc_100141FC
0x100141f5  mov     dword ptr [eax+24h], 1
0x100141fc  test    edi, edi
0x100141fe  js      short loc_10014210
0x10014200  mov     eax, edi
0x10014202  pop     edi
0x10014203  pop     esi
0x10014204  pop     ebx
0x10014205  mov     esp, ebp
0x10014207  pop     ebp
0x10014208  retn    4
0x1001420b  mov     edi, 8007000Eh
0x10014210  mov     ebx, [esi+0Ch]
0x10014213  test    ebx, ebx
0x10014215  jz      short loc_10014227
0x10014217  mov     ecx, ebx; this
0x10014219  call    ??1CImpIAccessor@@QAE@XZ; CImpIAccessor::~CImpIAccessor(void)
0x1001421e  push    ebx; Block
0x1001421f  call    ??3@YAXPAX@Z; operator delete(void *)
0x10014224  add     esp, 4
0x10014227  mov     eax, [esi+10h]
0x1001422a  test    eax, eax
0x1001422c  jz      short loc_1001423D
0x1001422e  push    eax; Block
0x1001422f  mov     dword ptr [eax], offset ??_7CImpICommandText@@6B@; const CImpICommandText::`vftable'
0x10014235  call    ??3@YAXPAX@Z; operator delete(void *)
0x1001423a  add     esp, 4
0x1001423d  mov     ebx, [esi+14h]
0x10014240  test    ebx, ebx
0x10014242  jz      short loc_1001425B
0x10014244  lea     ecx, [ebx+0Ch]; this
0x10014247  mov     dword ptr [ebx], offset ??_7CImpICommandProperties@@6B@; const CImpICommandProperties::`vftable'
0x1001424d  call    ??1CSettableProperties@@UAE@XZ; CSettableProperties::~CSettableProperties(void)
0x10014252  push    ebx; Block
0x10014253  call    ??3@YAXPAX@Z; operator delete(void *)
0x10014258  add     esp, 4
0x1001425b  mov     eax, [esi+18h]
0x1001425e  test    eax, eax
0x10014260  jz      short loc_10014271
0x10014262  push    eax; Block
0x10014263  mov     dword ptr [eax], offset ??_7CImpICommandPrepare@@6B@; const CImpICommandPrepare::`vftable'
0x10014269  call    ??3@YAXPAX@Z; operator delete(void *)
0x1001426e  add     esp, 4
0x10014271  mov     eax, [esi+1Ch]
0x10014274  test    eax, eax
0x10014276  jz      short loc_10014287
0x10014278  push    eax; Block
0x10014279  mov     dword ptr [eax], offset ??_7CImpICommandWithParameters@@6B@; const CImpICommandWithParameters::`vftable'
0x1001427f  call    ??3@YAXPAX@Z; operator delete(void *)
0x10014284  add     esp, 4
0x10014287  mov     eax, [esi+20h]
0x1001428a  test    eax, eax
0x1001428c  jz      short loc_1001429D
0x1001428e  push    eax; Block
0x1001428f  mov     dword ptr [eax], offset ??_7CImpIColumnsInfo@@6B@; const CImpIColumnsInfo::`vftable'
0x10014295  call    ??3@YAXPAX@Z; operator delete(void *)
0x1001429a  add     esp, 4
0x1001429d  mov     eax, [esi+24h]
0x100142a0  test    eax, eax
0x100142a2  jz      short loc_100142B3
0x100142a4  push    eax; Block
0x100142a5  mov     dword ptr [eax], offset ??_7CImpIColumnsRowset@@6B@; const CImpIColumnsRowset::`vftable'
0x100142ab  call    ??3@YAXPAX@Z; operator delete(void *)
0x100142b0  add     esp, 4
0x100142b3  mov     eax, [esi+28h]
0x100142b6  test    eax, eax
0x100142b8  jz      short loc_100142C9
0x100142ba  push    eax; Block
0x100142bb  mov     dword ptr [eax], offset ??_7CImpIConvertType@@6B@; const CImpIConvertType::`vftable'
0x100142c1  call    ??3@YAXPAX@Z; operator delete(void *)
0x100142c6  add     esp, 4
0x100142c9  mov     eax, [esi+2Ch]
0x100142cc  test    eax, eax
0x100142ce  jz      short loc_100142DF
0x100142d0  push    eax; Block
0x100142d1  mov     dword ptr [eax], offset ??_7CImpICommandPersist@@6B@; const CImpICommandPersist::`vftable'
0x100142d7  call    ??3@YAXPAX@Z; operator delete(void *)
0x100142dc  add     esp, 4
0x100142df  mov     eax, edi
0x100142e1  mov     dword ptr [esi+0Ch], 0
0x100142e8  pop     edi
0x100142e9  mov     dword ptr [esi+10h], 0
0x100142f0  mov     dword ptr [esi+14h], 0
0x100142f7  mov     dword ptr [esi+18h], 0
0x100142fe  mov     dword ptr [esi+1Ch], 0
0x10014305  mov     dword ptr [esi+20h], 0
0x1001430c  mov     dword ptr [esi+24h], 0
0x10014313  mov     dword ptr [esi+28h], 0
0x1001431a  mov     dword ptr [esi+2Ch], 0
0x10014321  pop     esi
0x10014322  pop     ebx
0x10014323  mov     esp, ebp
0x10014325  pop     ebp
0x10014326  retn    4
```
