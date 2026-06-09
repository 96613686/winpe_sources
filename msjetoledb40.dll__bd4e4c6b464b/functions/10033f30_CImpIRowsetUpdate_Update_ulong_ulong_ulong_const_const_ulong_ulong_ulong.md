# CImpIRowsetUpdate::Update(ulong,ulong,ulong const * const,ulong *,ulong * *,ulong * *)

- ea: `0x10033f30`
- end: `0x100340bc`
- name: `?Update@CImpIRowsetUpdate@@UAGJKKQBKPAKPAPAK2@Z`
- size: `396`
- prototype: `int(CImpIRowsetUpdate *__hidden this, unsigned int, unsigned int, const unsigned int *const, unsigned int *, unsigned int **, unsigned int **)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x1000ba90`
- `0x1001c380`
- `0x10033f30`
- `0x100340d0`
- `0x100495b0`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x100340a0`
- `KERNEL32!LeaveCriticalSection` at `0x100340a0`
- `KERNEL32!EnterCriticalSection` at `0x10033ff3`
- `KERNEL32!EnterCriticalSection` at `0x10033ff3`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10033f5e`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10033f5e`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10034048`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10034048`

## pseudocode

```c
int __stdcall CImpIRowsetUpdate::Update(
        CImpIRowsetUpdate *this,
        unsigned int a2,
        unsigned int a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned int **a6,
        unsigned int **a7)
{
  struct _RTL_CRITICAL_SECTION *v7; // esi
  struct _RTL_CRITICAL_SECTION *v8; // edx
  _DWORD *LockSemaphore; // eax
  CTransactionState *v10; // ecx
  int isZombie; // eax
  CImpIRowsetUpdate *v12; // ecx
  int v13; // edi
  unsigned int **v14; // edx
  int v15; // eax
  int v16; // eax
  const struct _GUID *v18; // [esp+0h] [ebp-28h]
  int v19; // [esp+4h] [ebp-24h]
  unsigned int **v20; // [esp+14h] [ebp-14h] BYREF
  unsigned int **v21; // [esp+18h] [ebp-10h]
  int v22; // [esp+24h] [ebp-4h]

  SetErrorInfo(0, 0);
  v7 = 0;
  v22 = 0;
  if ( a5 )
  {
    v21 = a7;
    *a5 = 0;
    v20 = a6;
  }
  else
  {
    v20 = 0;
    if ( a3 )
      v21 = a7;
    else
      v21 = 0;
  }
  v8 = (struct _RTL_CRITICAL_SECTION *)*((_DWORD *)this + 2);
  LockSemaphore = v8[2].LockSemaphore;
  if ( (!LockSemaphore
     || (LockSemaphore[4] != 1 || (v10 = (CTransactionState *)LockSemaphore[2]) == 0
       ? (isZombie = LockSemaphore[3])
       : (isZombie = CTransactionState::isZombie(v10)),
         isZombie != 1))
    && (v8[4].SpinCount || v8[9].SpinCount) )
  {
    if ( ((int)v8[4].DebugInfo & 0x400) != 0 )
    {
      v12 = this;
      v13 = -2147217888;
      goto LABEL_24;
    }
    v7 = v8 + 3;
    EnterCriticalSection(v8 + 3);
    if ( a3 && !a4 || (v14 = v20, a5) && !v20 )
    {
      v12 = this;
      v13 = -2147024809;
      goto LABEL_24;
    }
    v12 = this;
    v15 = *((_DWORD *)this + 2);
    if ( *(_DWORD *)(v15 + 236) )
    {
      if ( a3 || *(_DWORD *)(v15 + 220) == -1 )
      {
        v16 = CImpIRowsetUpdate::InternalUpdate(this, a2, a3, a4, a5, v20, v21, 0);
      }
      else
      {
        v20 = *(unsigned int ***)(v15 + 224);
        v16 = CImpIRowsetUpdate::InternalUpdate(this, a2, 1u, (const unsigned int *)&v20, a5, v14, v21, 1);
      }
      v13 = v16;
      goto LABEL_31;
    }
  }
  else
  {
    v12 = this;
  }
  v13 = -2147418113;
LABEL_24:
  if ( !JetGetDatabaseInfo(
          *(_DWORD *)(*(_DWORD *)(*((_DWORD *)v12 + 2) + 56) + 16),
          *(_DWORD *)(*(_DWORD *)(*((_DWORD *)v12 + 2) + 56) + 20),
          &v20,
          4,
          3) )
    CExtError::SendHRtoOLEAuto(v13, (__int128 *)&IID_IRowsetUpdate, 0, v18, v19);
LABEL_31:
  if ( v7 )
    LeaveCriticalSection(v7);
  return v13;
}

```

## disassembly

```asm
0x10033f30  mov     edi, edi
0x10033f32  push    ebp
0x10033f33  mov     ebp, esp
0x10033f35  push    0FFFFFFFFh
0x10033f37  push    offset ?DropColumn@CImpITableDef@@UAGJPAUtagDBID@@0@Z_SEH
0x10033f3c  mov     eax, large fs:0
0x10033f42  push    eax
0x10033f43  sub     esp, 0Ch
0x10033f46  push    ebx
0x10033f47  push    esi
0x10033f48  push    edi; int
0x10033f49  mov     eax, ___security_cookie
0x10033f4e  xor     eax, ebp
0x10033f50  push    eax; struct _GUID *
0x10033f51  lea     eax, [ebp+var_C]
0x10033f54  mov     large fs:0, eax
0x10033f5a  push    0; perrinfo
0x10033f5c  push    0; dwReserved
0x10033f5e  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10033f64  xor     esi, esi
0x10033f66  mov     [ebp+var_18], esi
0x10033f69  mov     edi, [ebp+arg_10]
0x10033f6c  mov     ebx, [ebp+arg_8]
0x10033f6f  mov     [ebp+var_4], esi
0x10033f72  test    edi, edi
0x10033f74  jnz     short loc_10033F8A
0x10033f76  mov     [ebp+var_14], esi
0x10033f79  test    ebx, ebx
0x10033f7b  jnz     short loc_10033F82
0x10033f7d  mov     [ebp+var_10], ebx
0x10033f80  jmp     short loc_10033F9C
0x10033f82  mov     ecx, [ebp+arg_18]
0x10033f85  mov     [ebp+var_10], ecx
0x10033f88  jmp     short loc_10033F9C
0x10033f8a  mov     eax, [ebp+arg_18]
0x10033f8d  mov     [ebp+var_10], eax
0x10033f90  mov     eax, [ebp+arg_14]
0x10033f93  mov     dword ptr [edi], 0
0x10033f99  mov     [ebp+var_14], eax
0x10033f9c  mov     eax, [ebp+this]
0x10033f9f  mov     edx, [eax+8]
0x10033fa2  mov     eax, [edx+40h]
0x10033fa5  test    eax, eax
0x10033fa7  jz      short loc_10033FC5
0x10033fa9  cmp     dword ptr [eax+10h], 1
0x10033fad  jnz     short loc_10033FBD
0x10033faf  mov     ecx, [eax+8]; this
0x10033fb2  test    ecx, ecx
0x10033fb4  jz      short loc_10033FBD
0x10033fb6  call    ?isZombie@CTransactionState@@QAEHXZ; CTransactionState::isZombie(void)
0x10033fbb  jmp     short loc_10033FC0
0x10033fbd  mov     eax, [eax+0Ch]
0x10033fc0  cmp     eax, 1
0x10033fc3  jz      short loc_10033FD4
0x10033fc5  cmp     dword ptr [edx+74h], 0
0x10033fc9  jnz     short loc_10033FD9
0x10033fcb  cmp     dword ptr [edx+0ECh], 0
0x10033fd2  jnz     short loc_10033FD9
0x10033fd4  mov     ecx, [ebp+this]
0x10033fd7  jmp     short loc_10034027
0x10033fd9  test    dword ptr [edx+60h], 400h
0x10033fe0  jz      short loc_10033FEC
0x10033fe2  mov     ecx, [ebp+this]
0x10033fe5  mov     edi, 80040E20h
0x10033fea  jmp     short loc_1003402C
0x10033fec  lea     esi, [edx+48h]
0x10033fef  push    esi; lpCriticalSection
0x10033ff0  mov     [ebp+var_18], esi
0x10033ff3  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10033ff9  test    ebx, ebx
0x10033ffb  jz      short loc_10034003
0x10033ffd  cmp     [ebp+arg_C], 0
0x10034001  jz      short loc_1003400E
0x10034003  mov     edx, [ebp+var_14]
0x10034006  test    edi, edi
0x10034008  jz      short loc_10034018
0x1003400a  test    edx, edx
0x1003400c  jnz     short loc_10034018
0x1003400e  mov     ecx, [ebp+this]
0x10034011  mov     edi, 80070057h
0x10034016  jmp     short loc_1003402C
0x10034018  mov     ecx, [ebp+this]; this
0x1003401b  mov     eax, [ecx+8]
0x1003401e  cmp     dword ptr [eax+0ECh], 0
0x10034025  jnz     short loc_10034061
0x10034027  mov     edi, 8000FFFFh
0x1003402c  mov     eax, [ecx+8]
0x1003402f  mov     eax, [eax+38h]
0x10034032  cmp     edi, 8007000Eh
0x10034038  jz      short loc_1003409B
0x1003403a  push    3
0x1003403c  push    4
0x1003403e  lea     ecx, [ebp+var_14]
0x10034041  push    ecx
0x10034042  push    dword ptr [eax+14h]
0x10034045  push    dword ptr [eax+10h]
0x10034048  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x1003404e  test    eax, eax
0x10034050  jnz     short loc_1003409B
0x10034052  push    eax; int
0x10034053  push    offset _IID_IRowsetUpdate; int
0x10034058  mov     edx, edi
0x1003405a  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x1003405f  jmp     short loc_1003409B
0x10034061  test    ebx, ebx
0x10034063  jnz     short loc_10034086
0x10034065  cmp     dword ptr [eax+0DCh], 0FFFFFFFFh
0x1003406c  jz      short loc_10034086
0x1003406e  mov     eax, [eax+0E0h]
0x10034074  push    1
0x10034076  push    [ebp+var_10]
0x10034079  mov     [ebp+var_14], eax
0x1003407c  lea     eax, [ebp+var_14]
0x1003407f  push    edx
0x10034080  push    edi
0x10034081  push    eax
0x10034082  push    1
0x10034084  jmp     short loc_10034091
0x10034086  push    0; int
0x10034088  push    [ebp+var_10]; unsigned int **
0x1003408b  push    edx; unsigned int **
0x1003408c  push    edi; unsigned int *
0x1003408d  push    [ebp+arg_C]; unsigned int *
0x10034090  push    ebx; unsigned int
0x10034091  push    [ebp+arg_4]; unsigned int
0x10034094  call    ?InternalUpdate@CImpIRowsetUpdate@@AAEJKKQBKPAKPAPAK2H@Z; CImpIRowsetUpdate::InternalUpdate(ulong,ulong,ulong const * const,ulong *,ulong * *,ulong * *,int)
0x10034099  mov     edi, eax
0x1003409b  test    esi, esi
0x1003409d  jz      short loc_100340A6
0x1003409f  push    esi; lpCriticalSection
0x100340a0  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100340a6  mov     eax, edi
0x100340a8  mov     ecx, [ebp+var_C]
0x100340ab  mov     large fs:0, ecx
0x100340b2  pop     ecx
0x100340b3  pop     edi
0x100340b4  pop     esi
0x100340b5  pop     ebx
0x100340b6  mov     esp, ebp
0x100340b8  pop     ebp
0x100340b9  retn    1Ch
0x1004dd50  lea     ecx, [ebp+var_18]; this
0x1004dd53  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004dd5d  nop
0x1004dd5e  nop
0x1004dd5f  mov     edx, [esp-4+arg_4]
0x1004dd63  lea     eax, [edx+0Ch]
0x1004dd66  mov     ecx, [edx-1Ch]
0x1004dd69  xor     ecx, eax; StackCookie
0x1004dd6b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004dd70  mov     eax, offset stru_1004F354
0x1004dd75  jmp     ___CxxFrameHandler3
```
