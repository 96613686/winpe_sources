# CImpICommandPersist::GetCurrentCommand(tagDBID * *)

- ea: `0x10011740`
- end: `0x100118a3`
- name: `?GetCurrentCommand@CImpICommandPersist@@UAGJPAPAUtagDBID@@@Z`
- size: `355`
- prototype: `int(CImpICommandPersist *__hidden this, struct tagDBID **)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1000ba90`
- `0x10011740`
- `0x1001c380`
- `0x1001c6d0`
- `0x100255a0`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x10011809`
- `KERNEL32!LeaveCriticalSection` at `0x10011809`
- `KERNEL32!EnterCriticalSection` at `0x10011784`
- `KERNEL32!EnterCriticalSection` at `0x10011784`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1001176e`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1001176e`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1001187c`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1001187c`

## pseudocode

```c
int __stdcall CImpICommandPersist::GetCurrentCommand(CImpICommandPersist *this, struct tagDBID **a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // esi
  int v3; // eax
  int String; // ebx
  struct tagDBID *v5; // eax
  struct tagDBID **v6; // eax
  int v8; // eax
  int v9; // ecx
  int v10; // eax
  int v11; // eax
  const struct _GUID *v12; // [esp+0h] [ebp-24h]
  int v13; // [esp+4h] [ebp-20h]
  _BYTE v14[4]; // [esp+10h] [ebp-14h] BYREF
  LPCRITICAL_SECTION v15; // [esp+14h] [ebp-10h]
  int v16; // [esp+20h] [ebp-4h]

  SetErrorInfo(0, 0);
  v15 = (LPCRITICAL_SECTION)(*((_DWORD *)this + 2) + 248);
  v2 = v15;
  EnterCriticalSection(v15);
  v16 = 0;
  if ( !a2 )
  {
    v3 = *((_DWORD *)this + 2);
    String = -2147024809;
    goto LABEL_18;
  }
  *a2 = 0;
  v3 = *((_DWORD *)this + 2);
  if ( !*(_DWORD *)(v3 + 72) )
  {
    String = -2147217817;
LABEL_18:
    v11 = *(_DWORD *)(v3 + 52);
    v9 = *(_DWORD *)(v11 + 20);
    v10 = *(_DWORD *)(v11 + 16);
    goto LABEL_19;
  }
  v5 = (struct tagDBID *)(*(int (__thiscall **)(_DWORD, int, int))(*(_DWORD *)Sys + 12))(
                           *(_DWORD *)(*(_DWORD *)Sys + 12),
                           Sys,
                           24);
  *a2 = v5;
  if ( !v5 )
  {
    String = -2147024882;
LABEL_6:
    v6 = a2;
LABEL_7:
    if ( *v6 )
    {
      if ( Sys )
        (*(void (__thiscall **)(_DWORD, int, struct tagDBID *))(*(_DWORD *)Sys + 20))(
          *(_DWORD *)(*(_DWORD *)Sys + 20),
          Sys,
          *v6);
      *a2 = 0;
    }
    goto LABEL_11;
  }
  v5->eKind = 2;
  String = CopyAndAllocateString(*(unsigned __int16 **)(*((_DWORD *)this + 2) + 76), &(*a2)->uName.pwszName);
  if ( String >= 0 )
    goto LABEL_11;
  v8 = *(_DWORD *)(*((_DWORD *)this + 2) + 52);
  v9 = *(_DWORD *)(v8 + 20);
  v10 = *(_DWORD *)(v8 + 16);
  if ( String == -2147024882 )
    goto LABEL_6;
LABEL_19:
  if ( !JetGetDatabaseInfo(v10, v9, v14, 4, 3) )
    CExtError::SendHRtoOLEAuto(String, (__int128 *)&IID_ICommandPersist, 0, v12, v13);
  v6 = a2;
  if ( a2 )
    goto LABEL_7;
LABEL_11:
  if ( v2 )
    LeaveCriticalSection(v2);
  return String;
}

```

## disassembly

```asm
0x10011740  mov     edi, edi
0x10011742  push    ebp
0x10011743  mov     ebp, esp
0x10011745  push    0FFFFFFFFh
0x10011747  push    offset ?StartTransaction@CImpITransactionLocal@@UAGJJKPAUITransactionOptions@@PAK@Z_SEH
0x1001174c  mov     eax, large fs:0
0x10011752  push    eax
0x10011753  sub     esp, 8
0x10011756  push    ebx
0x10011757  push    esi
0x10011758  push    edi; int
0x10011759  mov     eax, ___security_cookie
0x1001175e  xor     eax, ebp
0x10011760  push    eax; struct _GUID *
0x10011761  lea     eax, [ebp+var_C]
0x10011764  mov     large fs:0, eax
0x1001176a  push    0; perrinfo
0x1001176c  push    0; dwReserved
0x1001176e  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10011774  mov     edi, [ebp+this]
0x10011777  mov     esi, [edi+8]
0x1001177a  add     esi, 0F8h
0x10011780  push    esi; lpCriticalSection
0x10011781  mov     [ebp+var_10], esi
0x10011784  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1001178a  mov     ebx, [ebp+arg_4]
0x1001178d  mov     [ebp+var_4], 0
0x10011794  test    ebx, ebx
0x10011796  jz      loc_10011861
0x1001179c  mov     dword ptr [ebx], 0
0x100117a2  mov     eax, [edi+8]
0x100117a5  cmp     dword ptr [eax+48h], 0
0x100117a9  jnz     short loc_100117B5
0x100117ab  mov     ebx, 80040E67h
0x100117b0  jmp     loc_10011869
0x100117b5  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x100117bb  push    18h
0x100117bd  push    ecx
0x100117be  mov     eax, [ecx]
0x100117c0  mov     edi, [eax+0Ch]
0x100117c3  mov     ecx, edi
0x100117c5  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100117cb  call    edi
0x100117cd  mov     [ebx], eax
0x100117cf  test    eax, eax
0x100117d1  jnz     short loc_10011825
0x100117d3  mov     ebx, 8007000Eh
0x100117d8  mov     eax, [ebp+arg_4]
0x100117db  mov     edx, [eax]
0x100117dd  test    edx, edx
0x100117df  jz      short loc_10011804
0x100117e1  mov     eax, ?Sys@@3VSystem@@A; System Sys
0x100117e6  test    eax, eax
0x100117e8  jz      short loc_100117FB
0x100117ea  mov     ecx, [eax]
0x100117ec  push    edx
0x100117ed  push    eax
0x100117ee  mov     edi, [ecx+14h]
0x100117f1  mov     ecx, edi
0x100117f3  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100117f9  call    edi
0x100117fb  mov     eax, [ebp+arg_4]
0x100117fe  mov     dword ptr [eax], 0
0x10011804  test    esi, esi
0x10011806  jz      short loc_1001180F
0x10011808  push    esi; lpCriticalSection
0x10011809  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001180f  mov     eax, ebx
0x10011811  mov     ecx, [ebp+var_C]
0x10011814  mov     large fs:0, ecx
0x1001181b  pop     ecx
0x1001181c  pop     edi
0x1001181d  pop     esi
0x1001181e  pop     ebx
0x1001181f  mov     esp, ebp
0x10011821  pop     ebp
0x10011822  retn    8
0x10011825  mov     edi, [ebp+this]
0x10011828  mov     dword ptr [eax+10h], 2
0x1001182f  mov     edx, [ebx]
0x10011831  add     edx, 14h
0x10011834  mov     ecx, [edi+8]
0x10011837  mov     ecx, [ecx+4Ch]
0x1001183a  call    ?CopyAndAllocateString@@YGJPBGPAPAG@Z; CopyAndAllocateString(ushort const *,ushort * *)
0x1001183f  mov     ebx, eax
0x10011841  mov     edx, ebx
0x10011843  test    ebx, ebx
0x10011845  jns     short loc_10011804
0x10011847  mov     eax, [edi+8]
0x1001184a  mov     eax, [eax+34h]
0x1001184d  mov     ecx, [eax+14h]
0x10011850  mov     eax, [eax+10h]
0x10011853  cmp     edx, 8007000Eh
0x10011859  jz      loc_100117D8
0x1001185f  jmp     short loc_10011872
0x10011861  mov     eax, [edi+8]
0x10011864  mov     ebx, 80070057h
0x10011869  mov     eax, [eax+34h]
0x1001186c  mov     ecx, [eax+14h]
0x1001186f  mov     eax, [eax+10h]
0x10011872  push    3
0x10011874  push    4
0x10011876  lea     edx, [ebp+var_14]
0x10011879  push    edx
0x1001187a  push    ecx
0x1001187b  push    eax
0x1001187c  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x10011882  test    eax, eax
0x10011884  jnz     short loc_10011893
0x10011886  push    eax; int
0x10011887  push    offset _IID_ICommandPersist; int
0x1001188c  mov     edx, ebx
0x1001188e  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x10011893  mov     eax, [ebp+arg_4]
0x10011896  test    eax, eax
0x10011898  jz      loc_10011804
0x1001189e  jmp     loc_100117DB
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
