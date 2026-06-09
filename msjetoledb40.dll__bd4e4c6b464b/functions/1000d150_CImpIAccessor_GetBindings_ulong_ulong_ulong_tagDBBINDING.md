# CImpIAccessor::GetBindings(ulong,ulong *,ulong *,tagDBBINDING * *)

- ea: `0x1000d150`
- end: `0x1000d443`
- name: `?GetBindings@CImpIAccessor@@UAGJKPAK0PAPAUtagDBBINDING@@@Z`
- size: `755`
- prototype: `int(CImpIAccessor *__hidden this, unsigned int, unsigned int *, unsigned int *, struct tagDBBINDING **)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x1000ba50`
- `0x1000ba90`
- `0x1000bab0`
- `0x1000d150`
- `0x1001c380`
- `0x1001c6d0`
- `0x100495b0`
- `0x1004d406`
- `0x1004d420`
- `0x1004dc81`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1000d412`
- `KERNEL32!LeaveCriticalSection` at `0x1000d412`
- `KERNEL32!EnterCriticalSection` at `0x1000d18d`
- `KERNEL32!EnterCriticalSection` at `0x1000d18d`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1000d17d`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1000d17d`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1000d3ce`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1000d3ce`

## pseudocode

```c
int __stdcall CImpIAccessor::GetBindings(
        struct _RTL_CRITICAL_SECTION *this,
        unsigned int a2,
        unsigned int *a3,
        unsigned int *a4,
        struct tagDBBINDING **a5)
{
  struct _RTL_CRITICAL_SECTION *v5; // esi
  _DWORD *v6; // eax
  CTransactionState *v7; // ecx
  int isZombie; // eax
  struct tagDBBINDING **v9; // edi
  int v10; // edx
  unsigned int DWORDOfExtBuffer; // eax
  unsigned int v12; // edx
  struct tagDBBINDING *v13; // ecx
  unsigned int v14; // eax
  int v15; // ecx
  struct tagDBBINDING *v16; // eax
  int v17; // eax
  struct tagDBBINDING *v18; // ecx
  int v19; // edx
  int v20; // ecx
  int v21; // eax
  int v22; // esi
  int v23; // eax
  int DatabaseInfo; // eax
  CExtBuffer *v26; // [esp+0h] [ebp-2Ch]
  unsigned int v27; // [esp+4h] [ebp-28h]
  DBOBJECT *v28; // [esp+10h] [ebp-1Ch] BYREF
  int v29; // [esp+14h] [ebp-18h]
  _DWORD *RecursionCount; // [esp+18h] [ebp-14h]
  int v31; // [esp+1Ch] [ebp-10h]
  int v32; // [esp+28h] [ebp-4h]

  SetErrorInfo(0, 0);
  v5 = this + 1;
  EnterCriticalSection(this + 1);
  v32 = 0;
  if ( ((int)this->LockSemaphore & 1) != 0 )
  {
    RecursionCount = (_DWORD *)this->RecursionCount;
    if ( (*(int (__thiscall **)(_DWORD *))(*RecursionCount + 20))(RecursionCount) )
    {
      RecursionCount = (_DWORD *)this->RecursionCount;
      v6 = (_DWORD *)(*(int (__thiscall **)(_DWORD *))(*RecursionCount + 20))(RecursionCount);
      if ( v6[4] == 1 && (v7 = (CTransactionState *)v6[2]) != 0 )
        isZombie = CTransactionState::isZombie(v7);
      else
        isZombie = v6[3];
      if ( isZombie == 1 )
      {
        v9 = a5;
        v10 = -2147418113;
        goto LABEL_40;
      }
    }
  }
  if ( a4 )
    *a4 = 0;
  v9 = a5;
  if ( a5 )
    *a5 = 0;
  if ( !a2 )
  {
    v10 = -2147217920;
    goto LABEL_40;
  }
  if ( !a3 || !a4 || !a5 )
  {
    v10 = -2147024809;
    goto LABEL_40;
  }
  DWORDOfExtBuffer = CExtBuffer::GetDWORDOfExtBuffer(v26, v27);
  RecursionCount = (_DWORD *)DWORDOfExtBuffer;
  if ( !DWORDOfExtBuffer )
  {
    v10 = -2147217920;
    goto LABEL_40;
  }
  *a3 = *(_DWORD *)(DWORDOfExtBuffer + 16);
  v12 = *(_DWORD *)(DWORDOfExtBuffer + 36);
  *a4 = v12;
  if ( !v12 )
  {
    *a5 = 0;
LABEL_38:
    v10 = 0;
    v31 = 0;
    goto LABEL_49;
  }
  v9 = a5;
  v13 = (struct tagDBBINDING *)(*(int (__thiscall **)(_DWORD, int, unsigned int))(*(_DWORD *)Sys + 12))(
                                 *(_DWORD *)(*(_DWORD *)Sys + 12),
                                 Sys,
                                 52 * v12);
  *a5 = v13;
  if ( !v13 )
  {
    v10 = -2147024882;
    goto LABEL_40;
  }
  memcpy(v13, RecursionCount + 10, 52 * *a4);
  v14 = 0;
  v31 = 0;
  if ( !RecursionCount[9] )
    goto LABEL_38;
  while ( 1 )
  {
    v15 = v14;
    v16 = *v9;
    v29 = v15 * 52;
    if ( v16[v15].pObject )
      break;
LABEL_27:
    v14 = v31 + 1;
    v31 = v14;
    if ( v14 >= RecursionCount[9] )
    {
      v10 = 0;
      v31 = 0;
      goto LABEL_49;
    }
  }
  v17 = (*(int (__thiscall **)(_DWORD, int, int))(*(_DWORD *)Sys + 12))(*(_DWORD *)(*(_DWORD *)Sys + 12), Sys, 20);
  v28 = (DBOBJECT *)v17;
  if ( v17 )
  {
    v9 = a5;
    v19 = v29;
    v20 = *(int *)((char *)&(*a5)->pObject + v29);
    *(_OWORD *)v17 = *(_OWORD *)v20;
    *(_DWORD *)(v17 + 16) = *(_DWORD *)(v20 + 16);
    *(DBOBJECT **)((char *)&(*a5)->pObject + v19) = v28;
    goto LABEL_27;
  }
  if ( v31 )
  {
    v21 = Sys;
    v22 = v31;
    do
    {
      --v22;
      v18 = *a5;
      if ( (*a5)[v22].pObject && v21 )
      {
        (*(void (__thiscall **)(_DWORD, int, DBOBJECT *))(*(_DWORD *)v21 + 20))(
          *(_DWORD *)(*(_DWORD *)v21 + 20),
          v21,
          (*a5)[v22].pObject);
        v21 = Sys;
      }
    }
    while ( v22 );
    v5 = this + 1;
  }
  v9 = a5;
  System::Free(v18);
  v10 = -2147024882;
LABEL_40:
  v31 = v10;
  if ( v10 != -2147024882 )
  {
    v23 = *(_DWORD *)(this->RecursionCount + 4 * ((int)this->LockSemaphore & 1) + 52);
    DatabaseInfo = JetGetDatabaseInfo(*(_DWORD *)(v23 + 16), *(_DWORD *)(v23 + 20), &v28, 4, 3);
    v10 = v31;
    if ( !DatabaseInfo )
    {
      CExtError::SendHRtoOLEAuto(v31, (__int128 *)&IID_IAccessor, 0, (const struct _GUID *)v26, v27);
      v10 = v31;
    }
  }
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  if ( v9 )
    *v9 = 0;
LABEL_49:
  if ( !v5 )
    return v10;
  LeaveCriticalSection(v5);
  return v31;
}

```

## disassembly

```asm
0x1000d150  mov     edi, edi
0x1000d152  push    ebp
0x1000d153  mov     ebp, esp
0x1000d155  push    0FFFFFFFFh
0x1000d157  push    offset ?GetLiteralInfo@CImpIDBInfo@@UAGJKQBKPAKPAPAUtagDBLITERALINFO@@PAPAG@Z_SEH
0x1000d15c  mov     eax, large fs:0
0x1000d162  push    eax
0x1000d163  sub     esp, 14h
0x1000d166  push    esi
0x1000d167  push    edi; int
0x1000d168  mov     eax, ___security_cookie
0x1000d16d  xor     eax, ebp
0x1000d16f  push    eax; struct _GUID *
0x1000d170  lea     eax, [ebp+var_C]
0x1000d173  mov     large fs:0, eax
0x1000d179  push    0; perrinfo
0x1000d17b  push    0; dwReserved
0x1000d17d  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x1000d183  mov     esi, [ebp+this]
0x1000d186  add     esi, 18h
0x1000d189  push    esi; lpCriticalSection
0x1000d18a  mov     [ebp+var_20], esi
0x1000d18d  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1000d193  mov     ecx, [ebp+this]
0x1000d196  mov     [ebp+var_4], 0
0x1000d19d  test    byte ptr [ecx+10h], 1
0x1000d1a1  jz      short loc_1000D206
0x1000d1a3  mov     eax, [ecx+8]
0x1000d1a6  mov     [ebp+var_14], eax
0x1000d1a9  mov     eax, [eax]
0x1000d1ab  mov     edi, [eax+14h]
0x1000d1ae  mov     ecx, edi
0x1000d1b0  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1000d1b6  mov     ecx, [ebp+var_14]
0x1000d1b9  call    edi
0x1000d1bb  test    eax, eax
0x1000d1bd  jz      short loc_1000D203
0x1000d1bf  mov     eax, [ebp+this]
0x1000d1c2  mov     eax, [eax+8]
0x1000d1c5  mov     [ebp+var_14], eax
0x1000d1c8  mov     eax, [eax]
0x1000d1ca  mov     edi, [eax+14h]
0x1000d1cd  mov     ecx, edi
0x1000d1cf  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1000d1d5  mov     ecx, [ebp+var_14]
0x1000d1d8  call    edi
0x1000d1da  cmp     dword ptr [eax+10h], 1
0x1000d1de  jnz     short loc_1000D1EE
0x1000d1e0  mov     ecx, [eax+8]; this
0x1000d1e3  test    ecx, ecx
0x1000d1e5  jz      short loc_1000D1EE
0x1000d1e7  call    ?isZombie@CTransactionState@@QAEHXZ; CTransactionState::isZombie(void)
0x1000d1ec  jmp     short loc_1000D1F1
0x1000d1ee  mov     eax, [eax+0Ch]
0x1000d1f1  cmp     eax, 1
0x1000d1f4  jnz     short loc_1000D203
0x1000d1f6  mov     edi, [ebp+arg_10]
0x1000d1f9  mov     edx, 8000FFFFh
0x1000d1fe  jmp     loc_1000D3A5
0x1000d203  mov     ecx, [ebp+this]
0x1000d206  mov     eax, [ebp+arg_C]
0x1000d209  test    eax, eax
0x1000d20b  jz      short loc_1000D213
0x1000d20d  mov     dword ptr [eax], 0
0x1000d213  mov     edi, [ebp+arg_10]
0x1000d216  test    edi, edi
0x1000d218  jz      short loc_1000D220
0x1000d21a  mov     dword ptr [edi], 0
0x1000d220  mov     edx, [ebp+arg_4]
0x1000d223  test    edx, edx
0x1000d225  jnz     short loc_1000D231
0x1000d227  mov     edx, 80040E00h
0x1000d22c  jmp     loc_1000D3A5
0x1000d231  cmp     [ebp+arg_8], 0
0x1000d235  jz      loc_1000D3A0
0x1000d23b  test    eax, eax
0x1000d23d  jz      loc_1000D3A0
0x1000d243  test    edi, edi
0x1000d245  jz      loc_1000D3A0
0x1000d24b  mov     ecx, [ecx+14h]
0x1000d24e  call    ?GetDWORDOfExtBuffer@CExtBuffer@@QAGKK@Z; CExtBuffer::GetDWORDOfExtBuffer(ulong)
0x1000d253  mov     ecx, eax
0x1000d255  mov     [ebp+var_14], ecx
0x1000d258  test    ecx, ecx
0x1000d25a  jnz     short loc_1000D266
0x1000d25c  mov     edx, 80040E00h
0x1000d261  jmp     loc_1000D3A5
0x1000d266  mov     edx, [ebp+arg_8]
0x1000d269  mov     eax, [ecx+10h]
0x1000d26c  mov     [edx], eax
0x1000d26e  mov     eax, [ebp+arg_C]
0x1000d271  mov     edx, [ecx+24h]
0x1000d274  mov     [eax], edx
0x1000d276  test    edx, edx
0x1000d278  jz      loc_1000D393
0x1000d27e  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x1000d284  mov     eax, [ecx]
0x1000d286  mov     edi, [eax+0Ch]
0x1000d289  imul    eax, edx, 34h ; '4'
0x1000d28c  push    eax
0x1000d28d  push    ecx
0x1000d28e  mov     ecx, edi
0x1000d290  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1000d296  call    edi
0x1000d298  mov     edi, [ebp+arg_10]
0x1000d29b  mov     ecx, eax
0x1000d29d  mov     [edi], ecx
0x1000d29f  test    ecx, ecx
0x1000d2a1  jnz     short loc_1000D2AD
0x1000d2a3  mov     edx, 8007000Eh
0x1000d2a8  jmp     loc_1000D3A5
0x1000d2ad  mov     eax, [ebp+arg_C]
0x1000d2b0  imul    eax, [eax], 34h ; '4'
0x1000d2b3  push    eax; Size
0x1000d2b4  mov     eax, [ebp+var_14]
0x1000d2b7  add     eax, 28h ; '('
0x1000d2ba  push    eax; Src
0x1000d2bb  push    ecx; void *
0x1000d2bc  call    _memcpy
0x1000d2c1  mov     ecx, [ebp+var_14]
0x1000d2c4  xor     eax, eax
0x1000d2c6  add     esp, 0Ch
0x1000d2c9  mov     [ebp+var_10], eax
0x1000d2cc  cmp     [ecx+24h], eax
0x1000d2cf  jbe     loc_1000D399
0x1000d2d5  imul    ecx, eax, 34h ; '4'
0x1000d2d8  mov     eax, [edi]
0x1000d2da  mov     [ebp+var_18], ecx
0x1000d2dd  cmp     dword ptr [ecx+eax+14h], 0
0x1000d2e2  jz      short loc_1000D324
0x1000d2e4  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x1000d2ea  push    14h
0x1000d2ec  push    ecx
0x1000d2ed  mov     eax, [ecx]
0x1000d2ef  mov     edi, [eax+0Ch]
0x1000d2f2  mov     ecx, edi
0x1000d2f4  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1000d2fa  call    edi
0x1000d2fc  mov     [ebp+var_1C], eax
0x1000d2ff  test    eax, eax
0x1000d301  jz      short loc_1000D33D
0x1000d303  mov     edi, [ebp+arg_10]
0x1000d306  mov     edx, [ebp+var_18]
0x1000d309  mov     ecx, [edi]
0x1000d30b  mov     ecx, [ecx+edx+14h]
0x1000d30f  movups  xmm0, xmmword ptr [ecx]
0x1000d312  movups  xmmword ptr [eax], xmm0
0x1000d315  mov     ecx, [ecx+10h]
0x1000d318  mov     [eax+10h], ecx
0x1000d31b  mov     eax, [edi]
0x1000d31d  mov     ecx, [ebp+var_1C]
0x1000d320  mov     [eax+edx+14h], ecx
0x1000d324  mov     eax, [ebp+var_10]
0x1000d327  mov     ecx, [ebp+var_14]
0x1000d32a  inc     eax
0x1000d32b  mov     [ebp+var_10], eax
0x1000d32e  cmp     eax, [ecx+24h]
0x1000d331  jb      short loc_1000D2D5
0x1000d333  xor     edx, edx
0x1000d335  mov     [ebp+var_10], edx
0x1000d338  jmp     loc_1000D40D
0x1000d33d  cmp     [ebp+var_10], 0
0x1000d341  jz      short loc_1000D382
0x1000d343  mov     eax, ?Sys@@3VSystem@@A; System Sys
0x1000d348  mov     esi, [ebp+var_10]
0x1000d34b  nop     dword ptr [eax+eax+00h]
0x1000d350  mov     ecx, [ebp+arg_10]
0x1000d353  dec     esi
0x1000d354  imul    edx, esi, 34h ; '4'
0x1000d357  mov     ecx, [ecx]
0x1000d359  mov     edx, [edx+ecx+14h]
0x1000d35d  test    edx, edx
0x1000d35f  jz      short loc_1000D37B
0x1000d361  test    eax, eax
0x1000d363  jz      short loc_1000D37B
0x1000d365  mov     ecx, [eax]
0x1000d367  push    edx
0x1000d368  push    eax
0x1000d369  mov     edi, [ecx+14h]
0x1000d36c  mov     ecx, edi
0x1000d36e  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1000d374  call    edi
0x1000d376  mov     eax, ?Sys@@3VSystem@@A; System Sys
0x1000d37b  test    esi, esi
0x1000d37d  jnz     short loc_1000D350
0x1000d37f  mov     esi, [ebp+var_20]
0x1000d382  mov     edi, [ebp+arg_10]
0x1000d385  push    dword ptr [edi]
0x1000d387  call    ?Free@System@@QAEXPAX@Z; System::Free(void *)
0x1000d38c  mov     edx, 8007000Eh
0x1000d391  jmp     short loc_1000D3A5
0x1000d393  mov     dword ptr [edi], 0
0x1000d399  xor     edx, edx
0x1000d39b  mov     [ebp+var_10], edx
0x1000d39e  jmp     short loc_1000D40D
0x1000d3a0  mov     edx, 80070057h
0x1000d3a5  mov     eax, [ebp+this]
0x1000d3a8  mov     [ebp+var_10], edx
0x1000d3ab  mov     ecx, [eax+10h]
0x1000d3ae  mov     eax, [eax+8]
0x1000d3b1  and     ecx, 1
0x1000d3b4  mov     eax, [eax+ecx*4+34h]
0x1000d3b8  cmp     edx, 8007000Eh
0x1000d3be  jz      short loc_1000D3E9
0x1000d3c0  push    3
0x1000d3c2  push    4
0x1000d3c4  lea     ecx, [ebp+var_1C]
0x1000d3c7  push    ecx
0x1000d3c8  push    dword ptr [eax+14h]
0x1000d3cb  push    dword ptr [eax+10h]
0x1000d3ce  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x1000d3d4  mov     edx, [ebp+var_10]
0x1000d3d7  test    eax, eax
0x1000d3d9  jnz     short loc_1000D3E9
0x1000d3db  push    eax; int
0x1000d3dc  push    offset _IID_IAccessor; int
0x1000d3e1  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x1000d3e6  mov     edx, [ebp+var_10]
0x1000d3e9  mov     eax, [ebp+arg_8]
0x1000d3ec  test    eax, eax
0x1000d3ee  jz      short loc_1000D3F6
0x1000d3f0  mov     dword ptr [eax], 0
0x1000d3f6  mov     eax, [ebp+arg_C]
0x1000d3f9  test    eax, eax
0x1000d3fb  jz      short loc_1000D403
0x1000d3fd  mov     dword ptr [eax], 0
0x1000d403  test    edi, edi
0x1000d405  jz      short loc_1000D40D
0x1000d407  mov     dword ptr [edi], 0
0x1000d40d  test    esi, esi
0x1000d40f  jz      short loc_1000D42E
0x1000d411  push    esi; lpCriticalSection
0x1000d412  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1000d418  mov     eax, [ebp+var_10]
0x1000d41b  mov     ecx, [ebp+var_C]
0x1000d41e  mov     large fs:0, ecx
0x1000d425  pop     ecx
0x1000d426  pop     edi
0x1000d427  pop     esi
0x1000d428  mov     esp, ebp
0x1000d42a  pop     ebp
0x1000d42b  retn    14h
0x1000d42e  mov     eax, edx
0x1000d430  mov     ecx, [ebp+var_C]
0x1000d433  mov     large fs:0, ecx
0x1000d43a  pop     ecx
0x1000d43b  pop     edi
0x1000d43c  pop     esi
0x1000d43d  mov     esp, ebp
0x1000d43f  pop     ebp
0x1000d440  retn    14h
0x1004dd80  lea     ecx, [ebp+var_20]; this
0x1004dd83  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004dd8d  nop
0x1004dd8e  nop
0x1004dd8f  mov     edx, [esp-4+arg_4]
0x1004dd93  lea     eax, [edx+0Ch]
0x1004dd96  mov     ecx, [edx-20h]
0x1004dd99  xor     ecx, eax; StackCookie
0x1004dd9b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004dda0  mov     eax, offset stru_1004F380
0x1004dda5  jmp     ___CxxFrameHandler3
```
