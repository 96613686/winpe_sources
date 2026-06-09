# CImpIAccessor::AddRefAccessor(ulong,ulong *)

- ea: `0x1000ce70`
- end: `0x1000cfde`
- name: `?AddRefAccessor@CImpIAccessor@@UAGJKPAK@Z`
- size: `366`
- prototype: `int(CImpIAccessor *__hidden this, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1000ba90`
- `0x1000ce70`
- `0x1001c380`
- `0x1001c6d0`
- `0x100495b0`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1000cfc1`
- `KERNEL32!LeaveCriticalSection` at `0x1000cfc1`
- `KERNEL32!EnterCriticalSection` at `0x1000ceb5`
- `KERNEL32!EnterCriticalSection` at `0x1000ceb5`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1000cea5`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1000cea5`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1000cfa5`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1000cfa5`

## pseudocode

```c
int __stdcall CImpIAccessor::AddRefAccessor(CImpIAccessor *this, unsigned int a2, unsigned int *a3)
{
  CImpIAccessor *v3; // ebx
  _DWORD *v4; // eax
  CTransactionState *v5; // ecx
  int isZombie; // eax
  int v7; // ebx
  _DWORD *v8; // ebx
  int v10; // ecx
  int v11; // eax
  int v12; // eax
  const struct _GUID *v14; // [esp+0h] [ebp-28h]
  int v15; // [esp+4h] [ebp-24h]
  _BYTE v16[4]; // [esp+10h] [ebp-18h] BYREF
  char *v17; // [esp+14h] [ebp-14h]
  int v18; // [esp+18h] [ebp-10h]
  int v19; // [esp+24h] [ebp-4h]

  v18 = 0;
  SetErrorInfo(0, 0);
  v3 = this;
  v17 = (char *)this + 24;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  v19 = 0;
  if ( (*((_BYTE *)this + 16) & 1) != 0 )
  {
    v3 = this;
    if ( (*(int (__thiscall **)(_DWORD))(**((_DWORD **)this + 2) + 20))(*((_DWORD *)this + 2)) )
    {
      v4 = (_DWORD *)(*(int (__thiscall **)(_DWORD))(**((_DWORD **)this + 2) + 20))(*((_DWORD *)this + 2));
      if ( v4[4] == 1 && (v5 = (CTransactionState *)v4[2]) != 0 )
        isZombie = CTransactionState::isZombie(v5);
      else
        isZombie = v4[3];
      if ( isZombie == 1 )
      {
        v7 = -2147418113;
        goto LABEL_19;
      }
      v3 = this;
    }
  }
  if ( !a2 )
    goto LABEL_18;
  if ( a3 )
    *a3 = 0;
  v8 = (_DWORD *)*((_DWORD *)v3 + 5);
  if ( a2 > v8[6] + 8 * v8[5] - 1
    || (*(_BYTE *)(((a2 - v8[6]) >> 3) + v8[4]) & *((_BYTE *)&Bitmap::ThisBit + ((a2 - v8[6]) & 7))) != 0
    || (_mm_lfence(), (v10 = *(_DWORD *)(v8[2] + 4 * a2)) == 0) )
  {
LABEL_18:
    v7 = -2147217920;
LABEL_19:
    v18 = v7;
    v12 = *(_DWORD *)(*((_DWORD *)this + 2) + 4 * (*((_DWORD *)this + 4) & 1) + 52);
    if ( !JetGetDatabaseInfo(*(_DWORD *)(v12 + 16), *(_DWORD *)(v12 + 20), v16, 4, 3) )
      CExtError::SendHRtoOLEAuto(v7, (__int128 *)&IID_IAccessor, 0, v14, v15);
    goto LABEL_21;
  }
  v11 = *(_DWORD *)(v10 + 20) + 1;
  *(_DWORD *)(v10 + 20) = v11;
  if ( a3 )
    *a3 = v11;
LABEL_21:
  if ( this != (CImpIAccessor *)-24 )
    LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
  return v18;
}

```

## disassembly

```asm
0x1000ce70  mov     edi, edi
0x1000ce72  push    ebp
0x1000ce73  mov     ebp, esp
0x1000ce75  push    0FFFFFFFFh
0x1000ce77  push    offset ?Hash@CImpIRowsetLocate@@UAGJKKQBKQAPBEQAK2@Z_SEH
0x1000ce7c  mov     eax, large fs:0
0x1000ce82  push    eax
0x1000ce83  sub     esp, 0Ch
0x1000ce86  push    ebx
0x1000ce87  push    esi
0x1000ce88  push    edi; int
0x1000ce89  mov     eax, ___security_cookie
0x1000ce8e  xor     eax, ebp
0x1000ce90  push    eax; struct _GUID *
0x1000ce91  lea     eax, [ebp+var_C]
0x1000ce94  mov     large fs:0, eax
0x1000ce9a  push    0; perrinfo
0x1000ce9c  push    0; dwReserved
0x1000ce9e  mov     [ebp+var_10], 0
0x1000cea5  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x1000ceab  mov     ebx, [ebp+this]
0x1000ceae  lea     esi, [ebx+18h]
0x1000ceb1  push    esi; lpCriticalSection
0x1000ceb2  mov     [ebp+var_14], esi
0x1000ceb5  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1000cebb  mov     [ebp+var_4], 0
0x1000cec2  test    byte ptr [ebx+10h], 1
0x1000cec6  jz      short loc_1000CF1D
0x1000cec8  mov     ebx, [ebx+8]
0x1000cecb  mov     eax, [ebx]
0x1000cecd  mov     edi, [eax+14h]
0x1000ced0  mov     ecx, edi
0x1000ced2  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1000ced8  mov     ecx, ebx
0x1000ceda  call    edi
0x1000cedc  mov     ebx, [ebp+this]
0x1000cedf  test    eax, eax
0x1000cee1  jz      short loc_1000CF1D
0x1000cee3  mov     ebx, [ebx+8]
0x1000cee6  mov     eax, [ebx]
0x1000cee8  mov     edi, [eax+14h]
0x1000ceeb  mov     ecx, edi
0x1000ceed  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1000cef3  mov     ecx, ebx
0x1000cef5  call    edi
0x1000cef7  cmp     dword ptr [eax+10h], 1
0x1000cefb  jnz     short loc_1000CF0B
0x1000cefd  mov     ecx, [eax+8]; this
0x1000cf00  test    ecx, ecx
0x1000cf02  jz      short loc_1000CF0B
0x1000cf04  call    ?isZombie@CTransactionState@@QAEHXZ; CTransactionState::isZombie(void)
0x1000cf09  jmp     short loc_1000CF0E
0x1000cf0b  mov     eax, [eax+0Ch]
0x1000cf0e  cmp     eax, 1
0x1000cf11  jnz     short loc_1000CF1A
0x1000cf13  mov     ebx, 8000FFFFh
0x1000cf18  jmp     short loc_1000CF84
0x1000cf1a  mov     ebx, [ebp+this]
0x1000cf1d  mov     ecx, [ebp+arg_4]
0x1000cf20  test    ecx, ecx
0x1000cf22  jz      short loc_1000CF7F
0x1000cf24  mov     edi, [ebp+arg_8]
0x1000cf27  test    edi, edi
0x1000cf29  jz      short loc_1000CF31
0x1000cf2b  mov     dword ptr [edi], 0
0x1000cf31  mov     ebx, [ebx+14h]
0x1000cf34  mov     eax, [ebx+14h]
0x1000cf37  lea     eax, ds:0FFFFFFFFh[eax*8]
0x1000cf3e  add     eax, [ebx+18h]
0x1000cf41  cmp     ecx, eax
0x1000cf43  ja      short loc_1000CF7F
0x1000cf45  mov     eax, [ebx+10h]
0x1000cf48  mov     edx, ecx
0x1000cf4a  sub     edx, [ebx+18h]
0x1000cf4d  mov     ecx, edx
0x1000cf4f  and     edx, 7
0x1000cf52  shr     ecx, 3
0x1000cf55  mov     al, [ecx+eax]
0x1000cf58  test    ds:?ThisBit@Bitmap@@1QBEB[edx], al; uchar const * const Bitmap::ThisBit
0x1000cf5e  jnz     short loc_1000CF7F
0x1000cf60  mov     ecx, [ebp+arg_4]
0x1000cf63  lfence
0x1000cf66  mov     eax, [ebx+8]
0x1000cf69  mov     ecx, [eax+ecx*4]
0x1000cf6c  test    ecx, ecx
0x1000cf6e  jz      short loc_1000CF7F
0x1000cf70  mov     eax, [ecx+14h]
0x1000cf73  inc     eax
0x1000cf74  mov     [ecx+14h], eax
0x1000cf77  test    edi, edi
0x1000cf79  jz      short loc_1000CFBC
0x1000cf7b  mov     [edi], eax
0x1000cf7d  jmp     short loc_1000CFBC
0x1000cf7f  mov     ebx, 80040E00h
0x1000cf84  mov     eax, [ebp+this]
0x1000cf87  push    3
0x1000cf89  push    4
0x1000cf8b  mov     [ebp+var_10], ebx
0x1000cf8e  mov     ecx, [eax+10h]
0x1000cf91  mov     eax, [eax+8]
0x1000cf94  and     ecx, 1
0x1000cf97  mov     eax, [eax+ecx*4+34h]
0x1000cf9b  lea     ecx, [ebp+var_18]
0x1000cf9e  push    ecx
0x1000cf9f  push    dword ptr [eax+14h]
0x1000cfa2  push    dword ptr [eax+10h]
0x1000cfa5  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x1000cfab  test    eax, eax
0x1000cfad  jnz     short loc_1000CFBC
0x1000cfaf  push    eax; int
0x1000cfb0  push    offset _IID_IAccessor; int
0x1000cfb5  mov     edx, ebx
0x1000cfb7  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x1000cfbc  test    esi, esi
0x1000cfbe  jz      short loc_1000CFC7
0x1000cfc0  push    esi; lpCriticalSection
0x1000cfc1  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1000cfc7  mov     eax, [ebp+var_10]
0x1000cfca  mov     ecx, [ebp+var_C]
0x1000cfcd  mov     large fs:0, ecx
0x1000cfd4  pop     ecx
0x1000cfd5  pop     edi
0x1000cfd6  pop     esi
0x1000cfd7  pop     ebx
0x1000cfd8  mov     esp, ebp
0x1000cfda  pop     ebp
0x1000cfdb  retn    0Ch
0x1004dd20  lea     ecx, [ebp+var_14]; this
0x1004dd23  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004dd2d  nop
0x1004dd2e  nop
0x1004dd2f  mov     edx, [esp-4+arg_4]
0x1004dd33  lea     eax, [edx+0Ch]
0x1004dd36  mov     ecx, [edx-1Ch]
0x1004dd39  xor     ecx, eax; StackCookie
0x1004dd3b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004dd40  mov     eax, offset stru_1004F328
0x1004dd45  jmp     ___CxxFrameHandler3
```
