# CImpICommandText::GetDBSession(_GUID const &,IUnknown * *)

- ea: `0x100107b0`
- end: `0x100108a2`
- name: `?GetDBSession@CImpICommandText@@UAGJABU_GUID@@PAPAUIUnknown@@@Z`
- size: `242`
- prototype: `int(CImpICommandText *__hidden this, const struct _GUID *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1000ba90`
- `0x100107b0`
- `0x100147f0`
- `0x1001c380`
- `0x1001c6d0`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x10010886`
- `KERNEL32!LeaveCriticalSection` at `0x10010886`
- `KERNEL32!EnterCriticalSection` at `0x100107f4`
- `KERNEL32!EnterCriticalSection` at `0x100107f4`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x100107de`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x100107de`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10010866`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10010866`

## pseudocode

```c
int __stdcall CImpICommandText::GetDBSession(CImpICommandText *this, const struct _GUID *a2, struct IUnknown **a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // esi
  int v4; // eax
  int v5; // ecx
  int v6; // edi
  int v7; // eax
  int v8; // eax
  const struct _GUID *v10; // [esp+0h] [ebp-24h]
  int v11; // [esp+4h] [ebp-20h]
  _BYTE v12[4]; // [esp+10h] [ebp-14h] BYREF
  LPCRITICAL_SECTION v13; // [esp+14h] [ebp-10h]
  int v14; // [esp+20h] [ebp-4h]

  SetErrorInfo(0, 0);
  v13 = (LPCRITICAL_SECTION)(*((_DWORD *)this + 2) + 248);
  v3 = v13;
  EnterCriticalSection(v13);
  v14 = 0;
  CCommand::CheckForZombieCommandAndFix(*((_DWORD *)this + 2));
  v4 = *(_DWORD *)(*((_DWORD *)this + 2) + 52);
  if ( a3 )
  {
    v6 = (***(int (__thiscall ****)(_DWORD, _DWORD, const struct _GUID *, struct IUnknown **))(v4 + 28))(
           ***(_DWORD ***)(v4 + 28),
           *(_DWORD *)(v4 + 28),
           a2,
           a3);
    if ( v6 >= 0 )
    {
      v6 = 0;
      goto LABEL_8;
    }
    *a3 = 0;
    v8 = *(_DWORD *)(*((_DWORD *)this + 2) + 52);
    v5 = *(_DWORD *)(v8 + 20);
    v7 = *(_DWORD *)(v8 + 16);
    if ( v6 == -2147024882 )
      goto LABEL_8;
  }
  else
  {
    v5 = *(_DWORD *)(v4 + 20);
    v6 = -2147024809;
    v7 = *(_DWORD *)(v4 + 16);
  }
  if ( !JetGetDatabaseInfo(v7, v5, v12, 4, 3) )
    CExtError::SendHRtoOLEAuto(v6, (__int128 *)&IID_ICommand, 0, v10, v11);
LABEL_8:
  if ( v3 )
    LeaveCriticalSection(v3);
  return v6;
}

```

## disassembly

```asm
0x100107b0  mov     edi, edi
0x100107b2  push    ebp
0x100107b3  mov     ebp, esp
0x100107b5  push    0FFFFFFFFh
0x100107b7  push    offset ?StartTransaction@CImpITransactionLocal@@UAGJJKPAUITransactionOptions@@PAK@Z_SEH
0x100107bc  mov     eax, large fs:0
0x100107c2  push    eax
0x100107c3  sub     esp, 8
0x100107c6  push    ebx
0x100107c7  push    esi
0x100107c8  push    edi; int
0x100107c9  mov     eax, ___security_cookie
0x100107ce  xor     eax, ebp
0x100107d0  push    eax; struct _GUID *
0x100107d1  lea     eax, [ebp+var_C]
0x100107d4  mov     large fs:0, eax
0x100107da  push    0; perrinfo
0x100107dc  push    0; dwReserved
0x100107de  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x100107e4  mov     ebx, [ebp+this]
0x100107e7  mov     esi, [ebx+8]
0x100107ea  add     esi, 0F8h
0x100107f0  push    esi; lpCriticalSection
0x100107f1  mov     [ebp+var_10], esi
0x100107f4  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100107fa  mov     [ebp+var_4], 0
0x10010801  mov     ecx, [ebx+8]
0x10010804  call    ?CheckForZombieCommandAndFix@CCommand@@QAGJXZ; CCommand::CheckForZombieCommandAndFix(void)
0x10010809  mov     eax, [ebx+8]
0x1001080c  mov     edx, [ebp+arg_8]
0x1001080f  mov     eax, [eax+34h]
0x10010812  test    edx, edx
0x10010814  jnz     short loc_10010823
0x10010816  mov     ecx, [eax+14h]
0x10010819  mov     edi, 80070057h
0x1001081e  mov     eax, [eax+10h]
0x10010821  jmp     short loc_1001085C
0x10010823  mov     ecx, [eax+1Ch]
0x10010826  push    edx
0x10010827  push    [ebp+arg_4]
0x1001082a  mov     eax, [ecx]
0x1001082c  push    ecx
0x1001082d  mov     edi, [eax]
0x1001082f  mov     ecx, edi
0x10010831  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10010837  call    edi
0x10010839  mov     edi, eax
0x1001083b  test    edi, edi
0x1001083d  jns     short loc_1001087F
0x1001083f  mov     eax, [ebp+arg_8]
0x10010842  mov     dword ptr [eax], 0
0x10010848  mov     eax, [ebx+8]
0x1001084b  mov     eax, [eax+34h]
0x1001084e  mov     ecx, [eax+14h]
0x10010851  mov     eax, [eax+10h]
0x10010854  cmp     edi, 8007000Eh
0x1001085a  jz      short loc_10010881
0x1001085c  push    3
0x1001085e  push    4
0x10010860  lea     edx, [ebp+var_14]
0x10010863  push    edx
0x10010864  push    ecx
0x10010865  push    eax
0x10010866  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x1001086c  test    eax, eax
0x1001086e  jnz     short loc_10010881
0x10010870  push    eax; int
0x10010871  push    offset _IID_ICommand; int
0x10010876  mov     edx, edi
0x10010878  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x1001087d  jmp     short loc_10010881
0x1001087f  xor     edi, edi
0x10010881  test    esi, esi
0x10010883  jz      short loc_1001088C
0x10010885  push    esi; lpCriticalSection
0x10010886  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001088c  mov     eax, edi
0x1001088e  mov     ecx, [ebp+var_C]
0x10010891  mov     large fs:0, ecx
0x10010898  pop     ecx
0x10010899  pop     edi
0x1001089a  pop     esi
0x1001089b  pop     ebx
0x1001089c  mov     esp, ebp
0x1001089e  pop     ebp
0x1001089f  retn    0Ch
0x1004ddb0  lea     ecx, [ebp+var_10]; this
0x1004ddb3  jmp     ??1CMutex@@QAE@XZ
0x1004ddbd  nop
0x1004ddbe  nop
0x1004ddbf  mov     edx, [esp-4+arg_4]
0x1004ddc3  lea     eax, [edx+0Ch]
0x1004ddc6  mov     ecx, [edx-18h]
0x1004ddc9  xor     ecx, eax; StackCookie
0x1004ddcb  call    @__security_check_cookie@4
0x1004ddd0  mov     eax, offset stru_1004F3AC
0x1004ddd5  jmp     ___CxxFrameHandler3
```
