# CImpIAccessor::ReleaseAccessor(ulong,ulong *)

- ea: `0x1000cff0`
- end: `0x1000d13e`
- name: `?ReleaseAccessor@CImpIAccessor@@UAGJKPAK@Z`
- size: `334`
- prototype: `int(CImpIAccessor *__hidden this, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1000ba90`
- `0x1000bb00`
- `0x1000cff0`
- `0x1000d450`
- `0x1001c380`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1000d122`
- `KERNEL32!LeaveCriticalSection` at `0x1000d122`
- `KERNEL32!EnterCriticalSection` at `0x1000d02e`
- `KERNEL32!EnterCriticalSection` at `0x1000d02e`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1000d01e`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1000d01e`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1000d106`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1000d106`

## pseudocode

```c
int __stdcall CImpIAccessor::ReleaseAccessor(CImpIAccessor *this, unsigned int a2, unsigned int *a3)
{
  int v3; // ebx
  int v4; // eax
  _DWORD *v5; // eax
  int v7; // edx
  int v8; // eax
  int v9; // eax
  CImpIAccessor *v11; // [esp+0h] [ebp-28h]
  struct tagREDACCESSOR *v12; // [esp+4h] [ebp-24h]
  int v13; // [esp+14h] [ebp-14h] BYREF
  _DWORD *v14; // [esp+18h] [ebp-10h]
  int v15; // [esp+24h] [ebp-4h]

  v3 = 0;
  SetErrorInfo(0, 0);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  v15 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a2
    && (v14 = (_DWORD *)*((_DWORD *)this + 5), v4 = v14[5], v13 = v14[6], a2 <= v13 + 8 * v4 - 1)
    && (*(_BYTE *)(((a2 - v13) >> 3) + v14[4]) & *((_BYTE *)&Bitmap::ThisBit + ((a2 - v13) & 7))) == 0
    && (v5 = v14, _mm_lfence(), (v7 = *(_DWORD *)(v5[2] + 4 * a2)) != 0) )
  {
    v8 = *(_DWORD *)(v7 + 20);
    if ( v8 == 1 && (*((_BYTE *)this + 16) & 1) != 0 )
    {
      v13 = *(_DWORD *)(v7 + 20);
      if ( *(_DWORD *)(*((_DWORD *)this + 2) + 184) == a2 )
      {
        v8 = *(_DWORD *)(v7 + 20) + 1;
        *(_DWORD *)(v7 + 20) = v8;
      }
      else
      {
        v8 = v13;
      }
    }
    *(_DWORD *)(v7 + 20) = v8 - 1;
    if ( a3 )
      *a3 = v8 - 1;
    if ( !*(_DWORD *)(v7 + 20) )
    {
      CImpIAccessor::DeleteRedAccessor(v11, v12);
      CExtBuffer::DeleteFromExtBuffer(*((_DWORD **)this + 5), a2);
    }
  }
  else
  {
    v3 = -2147217920;
    v9 = *(_DWORD *)(*((_DWORD *)this + 2) + 4 * (*((_DWORD *)this + 4) & 1) + 52);
    if ( !JetGetDatabaseInfo(*(_DWORD *)(v9 + 16), *(_DWORD *)(v9 + 20), &v13, 4, 3) )
      CExtError::SendHRtoOLEAuto(-2147217920, (__int128 *)&IID_IAccessor, 0, (const struct _GUID *)v11, (int)v12);
  }
  if ( this != (CImpIAccessor *)-24 )
    LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
  return v3;
}

```

## disassembly

```asm
0x1000cff0  mov     edi, edi
0x1000cff2  push    ebp
0x1000cff3  mov     ebp, esp
0x1000cff5  push    0FFFFFFFFh
0x1000cff7  push    offset ?DropColumn@CImpITableDef@@UAGJPAUtagDBID@@0@Z_SEH
0x1000cffc  mov     eax, large fs:0
0x1000d002  push    eax
0x1000d003  sub     esp, 0Ch
0x1000d006  push    ebx
0x1000d007  push    esi
0x1000d008  push    edi; int
0x1000d009  mov     eax, ___security_cookie
0x1000d00e  xor     eax, ebp
0x1000d010  push    eax; struct _GUID *
0x1000d011  lea     eax, [ebp+var_C]
0x1000d014  mov     large fs:0, eax
0x1000d01a  xor     ebx, ebx
0x1000d01c  push    ebx; perrinfo
0x1000d01d  push    ebx; dwReserved
0x1000d01e  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x1000d024  mov     edi, [ebp+this]
0x1000d027  lea     esi, [edi+18h]
0x1000d02a  push    esi; lpCriticalSection
0x1000d02b  mov     [ebp+var_18], esi
0x1000d02e  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1000d034  mov     eax, [ebp+arg_8]
0x1000d037  mov     [ebp+var_4], ebx
0x1000d03a  test    eax, eax
0x1000d03c  jz      short loc_1000D040
0x1000d03e  mov     [eax], ebx
0x1000d040  mov     ecx, [ebp+arg_4]
0x1000d043  test    ecx, ecx
0x1000d045  jz      loc_1000D0E6
0x1000d04b  mov     eax, [edi+14h]
0x1000d04e  mov     [ebp+var_10], eax
0x1000d051  mov     edx, [eax+18h]
0x1000d054  mov     eax, [eax+14h]
0x1000d057  mov     [ebp+var_14], edx
0x1000d05a  lea     eax, ds:0FFFFFFFFh[eax*8]
0x1000d061  add     eax, edx
0x1000d063  cmp     ecx, eax
0x1000d065  ja      short loc_1000D0E6
0x1000d067  mov     eax, [ebp+var_10]
0x1000d06a  mov     edx, ecx
0x1000d06c  sub     edx, [ebp+var_14]
0x1000d06f  mov     ecx, edx
0x1000d071  and     edx, 7
0x1000d074  shr     ecx, 3
0x1000d077  mov     eax, [eax+10h]
0x1000d07a  mov     al, [ecx+eax]
0x1000d07d  test    ds:?ThisBit@Bitmap@@1QBEB[edx], al; uchar const * const Bitmap::ThisBit
0x1000d083  jnz     short loc_1000D0E6
0x1000d085  mov     eax, [ebp+var_10]
0x1000d088  mov     ecx, [ebp+arg_4]
0x1000d08b  lfence
0x1000d08e  mov     eax, [eax+8]
0x1000d091  mov     edx, [eax+ecx*4]
0x1000d094  test    edx, edx
0x1000d096  jz      short loc_1000D0E6
0x1000d098  mov     eax, [edx+14h]
0x1000d09b  cmp     eax, 1
0x1000d09e  jnz     short loc_1000D0BF
0x1000d0a0  test    [edi+10h], al
0x1000d0a3  jz      short loc_1000D0BF
0x1000d0a5  mov     [ebp+var_14], eax
0x1000d0a8  mov     eax, [edi+8]
0x1000d0ab  cmp     [eax+0B8h], ecx
0x1000d0b1  jnz     short loc_1000D0BC
0x1000d0b3  mov     eax, [edx+14h]
0x1000d0b6  inc     eax
0x1000d0b7  mov     [edx+14h], eax
0x1000d0ba  jmp     short loc_1000D0BF
0x1000d0bc  mov     eax, [ebp+var_14]
0x1000d0bf  lea     ecx, [eax-1]
0x1000d0c2  mov     eax, [ebp+arg_8]
0x1000d0c5  mov     [edx+14h], ecx
0x1000d0c8  test    eax, eax
0x1000d0ca  jz      short loc_1000D0CE
0x1000d0cc  mov     [eax], ecx
0x1000d0ce  cmp     dword ptr [edx+14h], 0
0x1000d0d2  jnz     short loc_1000D11D
0x1000d0d4  call    ?DeleteRedAccessor@CImpIAccessor@@AAGXPAUtagREDACCESSOR@@@Z; CImpIAccessor::DeleteRedAccessor(tagREDACCESSOR *)
0x1000d0d9  mov     edx, [ebp+arg_4]
0x1000d0dc  mov     ecx, [edi+14h]
0x1000d0df  call    ?DeleteFromExtBuffer@CExtBuffer@@QAGXK@Z; CExtBuffer::DeleteFromExtBuffer(ulong)
0x1000d0e4  jmp     short loc_1000D11D
0x1000d0e6  mov     ecx, [edi+10h]
0x1000d0e9  mov     ebx, 80040E00h
0x1000d0ee  mov     eax, [edi+8]
0x1000d0f1  and     ecx, 1
0x1000d0f4  push    3
0x1000d0f6  push    4
0x1000d0f8  mov     eax, [eax+ecx*4+34h]
0x1000d0fc  lea     ecx, [ebp+var_14]
0x1000d0ff  push    ecx
0x1000d100  push    dword ptr [eax+14h]
0x1000d103  push    dword ptr [eax+10h]
0x1000d106  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x1000d10c  test    eax, eax
0x1000d10e  jnz     short loc_1000D11D
0x1000d110  push    eax; int
0x1000d111  push    offset _IID_IAccessor; int
0x1000d116  mov     edx, ebx
0x1000d118  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x1000d11d  test    esi, esi
0x1000d11f  jz      short loc_1000D128
0x1000d121  push    esi; lpCriticalSection
0x1000d122  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1000d128  mov     eax, ebx
0x1000d12a  mov     ecx, [ebp+var_C]
0x1000d12d  mov     large fs:0, ecx
0x1000d134  pop     ecx
0x1000d135  pop     edi
0x1000d136  pop     esi
0x1000d137  pop     ebx
0x1000d138  mov     esp, ebp
0x1000d13a  pop     ebp
0x1000d13b  retn    0Ch
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
