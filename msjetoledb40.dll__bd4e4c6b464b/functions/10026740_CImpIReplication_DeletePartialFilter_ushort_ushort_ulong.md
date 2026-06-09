# CImpIReplication::DeletePartialFilter(ushort *,ushort *,ulong)

- ea: `0x10026740`
- end: `0x10026888`
- name: `?DeletePartialFilter@CImpIReplication@@UAGJPAG0K@Z`
- size: `328`
- prototype: `int(CImpIReplication *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x1000ba90`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001c6d0`
- `0x10026740`
- `0x10027860`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1002686c`
- `KERNEL32!LeaveCriticalSection` at `0x1002686c`
- `KERNEL32!EnterCriticalSection` at `0x10026790`
- `KERNEL32!EnterCriticalSection` at `0x10026790`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10026780`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10026780`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10026850`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10026850`

## pseudocode

```c
int __stdcall CImpIReplication::DeletePartialFilter(
        CImpIReplication *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int a4)
{
  int v4; // eax
  int v5; // ecx
  int v6; // eax
  struct _RTL_CRITICAL_SECTION *v7; // esi
  CReplCover *v8; // edi
  signed int v9; // eax
  int v10; // edi
  const struct _GUID *v12; // [esp+0h] [ebp-2Ch]
  const struct _GUID *v13; // [esp+4h] [ebp-28h]
  int v14; // [esp+14h] [ebp-18h] BYREF
  int v15; // [esp+18h] [ebp-14h]
  int v16; // [esp+1Ch] [ebp-10h]
  int v17; // [esp+28h] [ebp-4h]

  v4 = *((_DWORD *)this + 2);
  v5 = *(_DWORD *)(v4 + 16);
  v6 = *(_DWORD *)(v4 + 20);
  v14 = v5;
  v15 = v6;
  SetErrorInfo(0, 0);
  v7 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 104);
  EnterCriticalSection(v7);
  v17 = 0;
  if ( !a2 || !a3 && a4 == 2 )
    goto LABEL_15;
  if ( a4 == 1 )
  {
    v16 = 1;
    goto LABEL_8;
  }
  if ( a4 != 2 )
  {
LABEL_15:
    v10 = -2147024809;
    if ( !JetGetDatabaseInfo(
            *(_DWORD *)(*((_DWORD *)this + 2) + 16),
            *(_DWORD *)(*((_DWORD *)this + 2) + 20),
            &v14,
            4,
            3) )
      CExtError::SendHRtoOLEAuto(-2147024809, (__int128 *)&IID_IReplication, 0, v12, (int)v13);
    goto LABEL_17;
  }
  v16 = 2;
LABEL_8:
  v8 = (CReplCover *)*((_DWORD *)this + 4);
  if ( CReplCover::Initialize(v8) < 0 )
  {
    v9 = -1029;
    v10 = -2147467259;
LABEL_13:
    CExtError::SendJetErrortoOLEAuto(
      v10,
      *(char **)(*((_DWORD *)this + 2) + 16),
      v9,
      (int)&IID_IReplication,
      (int)v12,
      v13);
    goto LABEL_17;
  }
  v9 = (*(int (__thiscall **)(_DWORD, int, int, unsigned __int16 *, unsigned __int16 *, int))(*((_DWORD *)v8 + 2) + 32))(
         *(_DWORD *)(*((_DWORD *)v8 + 2) + 32),
         v14,
         v15,
         a2,
         a3,
         v16);
  if ( v9 < 0 )
  {
    v10 = -2147467259;
    goto LABEL_13;
  }
  v10 = 0;
  if ( v9 )
    goto LABEL_13;
  v10 = 0;
LABEL_17:
  if ( v7 )
    LeaveCriticalSection(v7);
  return v10;
}

```

## disassembly

```asm
0x10026740  mov     edi, edi
0x10026742  push    ebp
0x10026743  mov     ebp, esp
0x10026745  push    0FFFFFFFFh
0x10026747  push    offset ?IsSameRow@CImpIRowsetIdentity@@UAGJKK@Z_SEH
0x1002674c  mov     eax, large fs:0
0x10026752  push    eax
0x10026753  sub     esp, 10h
0x10026756  push    ebx
0x10026757  push    esi
0x10026758  push    edi; int
0x10026759  mov     eax, ___security_cookie
0x1002675e  xor     eax, ebp
0x10026760  push    eax; struct _GUID *
0x10026761  lea     eax, [ebp+var_C]
0x10026764  mov     large fs:0, eax
0x1002676a  mov     ebx, [ebp+this]
0x1002676d  push    0; perrinfo
0x1002676f  push    0; dwReserved
0x10026771  mov     eax, [ebx+8]
0x10026774  mov     ecx, [eax+10h]
0x10026777  mov     eax, [eax+14h]
0x1002677a  mov     [ebp+var_18], ecx
0x1002677d  mov     [ebp+var_14], eax
0x10026780  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10026786  mov     esi, [ebx+8]
0x10026789  add     esi, 68h ; 'h'
0x1002678c  push    esi; lpCriticalSection
0x1002678d  mov     [ebp+var_1C], esi
0x10026790  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10026796  cmp     [ebp+arg_4], 0
0x1002679a  mov     [ebp+var_4], 0
0x100267a1  jz      loc_1002683A
0x100267a7  cmp     [ebp+arg_8], 0
0x100267ab  mov     eax, [ebp+arg_C]
0x100267ae  jnz     short loc_100267B9
0x100267b0  cmp     eax, 2
0x100267b3  jz      loc_1002683A
0x100267b9  sub     eax, 1
0x100267bc  jz      short loc_100267CC
0x100267be  sub     eax, 1
0x100267c1  jnz     short loc_1002683A
0x100267c3  mov     [ebp+var_10], 2
0x100267ca  jmp     short loc_100267D3
0x100267cc  mov     [ebp+var_10], 1
0x100267d3  mov     edi, [ebx+10h]
0x100267d6  mov     ecx, edi; this
0x100267d8  call    ?Initialize@CReplCover@@QAEJXZ; CReplCover::Initialize(void)
0x100267dd  test    eax, eax
0x100267df  jns     short loc_100267ED
0x100267e1  mov     eax, 0FFFFFBFBh
0x100267e6  mov     edi, 80004005h
0x100267eb  jmp     short loc_10026821
0x100267ed  push    [ebp+var_10]
0x100267f0  mov     eax, [edi+8]
0x100267f3  push    [ebp+arg_8]
0x100267f6  push    [ebp+arg_4]
0x100267f9  mov     edi, [eax+20h]
0x100267fc  mov     ecx, edi
0x100267fe  push    [ebp+var_14]
0x10026801  push    [ebp+var_18]
0x10026804  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1002680a  call    edi
0x1002680c  mov     ecx, eax
0x1002680e  test    ecx, ecx
0x10026810  jns     short loc_10026819
0x10026812  mov     edi, 80004005h
0x10026817  jmp     short loc_10026821
0x10026819  xor     edi, edi
0x1002681b  mov     eax, ecx
0x1002681d  test    ecx, ecx
0x1002681f  jz      short loc_10026836
0x10026821  mov     ecx, [ebx+8]
0x10026824  mov     edx, edi
0x10026826  push    offset _IID_IReplication; int
0x1002682b  push    eax; unsigned int
0x1002682c  mov     ecx, [ecx+10h]
0x1002682f  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x10026834  jmp     short loc_10026867
0x10026836  xor     edi, edi
0x10026838  jmp     short loc_10026867
0x1002683a  mov     eax, [ebx+8]
0x1002683d  lea     ecx, [ebp+var_18]
0x10026840  push    3
0x10026842  push    4
0x10026844  push    ecx
0x10026845  push    dword ptr [eax+14h]
0x10026848  mov     edi, 80070057h
0x1002684d  push    dword ptr [eax+10h]
0x10026850  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x10026856  test    eax, eax
0x10026858  jnz     short loc_10026867
0x1002685a  push    eax; int
0x1002685b  push    offset _IID_IReplication; int
0x10026860  mov     edx, edi
0x10026862  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x10026867  test    esi, esi
0x10026869  jz      short loc_10026872
0x1002686b  push    esi; lpCriticalSection
0x1002686c  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10026872  mov     eax, edi
0x10026874  mov     ecx, [ebp+var_C]
0x10026877  mov     large fs:0, ecx
0x1002687e  pop     ecx
0x1002687f  pop     edi
0x10026880  pop     esi
0x10026881  pop     ebx
0x10026882  mov     esp, ebp
0x10026884  pop     ebp
0x10026885  retn    10h
0x1004e950  lea     ecx, [ebp+var_1C]; this
0x1004e953  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004e95d  nop
0x1004e95e  nop
0x1004e95f  mov     edx, [esp-4+arg_4]
0x1004e963  lea     eax, [edx+0Ch]
0x1004e966  mov     ecx, [edx-20h]
0x1004e969  xor     ecx, eax; StackCookie
0x1004e96b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004e970  mov     eax, offset stru_1004FC60
0x1004e975  jmp     ___CxxFrameHandler3
```
