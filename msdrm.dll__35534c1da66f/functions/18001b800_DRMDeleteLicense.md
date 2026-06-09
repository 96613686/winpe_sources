# DRMDeleteLicense

- ea: `0x18001b800`
- end: `0x18001ba31`
- name: `DRMDeleteLicense`
- size: `561`
- prototype: `HRESULT __stdcall(DRMHSESSION hSession, PWSTR wszLicenseId)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180019a30`
- `0x18001c610`

## callees

- `0x180001284`
- `0x18000420c`
- `0x18000442c`
- `0x1800046c8`
- `0x18001b800`
- `0x18001fa40`
- `0x1800208e8`
- `0x18002398c`
- `0x180035e48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b95b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b9b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b9bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b95b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b9b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b9bd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b8d8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b9a1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b8d8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b9a1`

## string_xrefs

- `0x18001b817`: `[msdrm]:+DRMDeleteLicense wszLicenseId=%S\n`
- `0x18001ba10`: `[msdrm]:-DRMDeleteLicense HR=%x\n`

## pseudocode

```c
HRESULT __stdcall DRMDeleteLicense(DRMHSESSION hSession, PWSTR wszLicenseId)
{
  __int64 v4; // r8
  __int64 v5; // r9
  volatile signed __int32 *Pointer; // rax
  volatile signed __int32 *v7; // rsi
  HRESULT v8; // ebx
  CHandleTable *v9; // rcx
  __int64 v10; // rdi
  void *v11; // rbx
  CDRMClient *v12; // rbx
  HRESULT v13; // eax
  void *v14; // rdi
  __int64 v15; // rbx
  struct _RTL_CRITICAL_SECTION *v16; // rcx
  _QWORD v18[5]; // [rsp+30h] [rbp-28h] BYREF
  void *Block; // [rsp+70h] [rbp+18h] BYREF

  _RTLTRACE("[msdrm]:+DRMDeleteLicense wszLicenseId=%S\n", wszLicenseId);
  if ( !hSession || !(unsigned __int8)DRMIsValidStringT<unsigned short>(wszLicenseId, 0, v4, v5) )
  {
    v8 = -2147024809;
    goto LABEL_40;
  }
  Pointer = (volatile signed __int32 *)DRMCInt::GetPointer(1u, hSession);
  v7 = Pointer;
  if ( !Pointer )
  {
    v8 = -2147024890;
    goto LABEL_40;
  }
  v9 = (CHandleTable *)(unsigned int)(*Pointer - 2);
  if ( *Pointer == 2 )
  {
    Block = 0;
    if ( CHandleTable::Get(v9, hSession, (struct DRMCInt **)&Block) >= 0 && (v14 = Block) != 0 )
    {
      if ( *(_DWORD *)Block == 2 )
      {
        v15 = *((_QWORD *)Block + 1);
        EnterCriticalSection((LPCRITICAL_SECTION)(v15 + 88));
        v16 = (struct _RTL_CRITICAL_SECTION *)(v15 + 88);
        if ( *(_DWORD *)(v15 + 136) == -1 )
        {
          v12 = 0;
          LeaveCriticalSection(v16);
        }
        else
        {
          LeaveCriticalSection(v16);
          v12 = (CDRMClient *)*((_QWORD *)v14 + 1);
        }
      }
      else
      {
        v12 = 0;
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v14 + 4, 0xFFFFFFFF) == 1 )
        operator delete(v14);
    }
    else
    {
      v12 = 0;
    }
  }
  else
  {
    if ( *Pointer != 3 )
    {
LABEL_7:
      v8 = -2147024890;
      goto LABEL_37;
    }
    Block = 0;
    if ( CHandleTable::Get(v9, hSession, (struct DRMCInt **)&Block) >= 0 && (v11 = Block) != 0 )
    {
      v10 = 0;
      if ( *(_DWORD *)Block == 3 && (int)CDRMReader::IsInitialized(*((CDRMReader **)Block + 1)) >= 0 )
        v10 = *((_QWORD *)v11 + 1);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v11 + 4, 0xFFFFFFFF) == 1 )
        operator delete(v11);
    }
    else
    {
      v10 = 0;
    }
    v12 = 0;
    if ( v10 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v10 + 88));
      v18[0] = *(_QWORD *)(v10 + 176);
      v18[1] = *(_QWORD *)(v10 + 184);
      if ( wszLicenseId )
      {
        v13 = DeletePersistedLicense(2, 0, 2, v18, wszLicenseId);
        v8 = v13;
        if ( v13 )
        {
          if ( v13 == -2147168454 )
          {
            v8 = DeletePersistedLicense(4, 0, 0, 0, wszLicenseId);
            if ( !v8 )
              *(_DWORD *)(v10 + 316) = 1;
          }
        }
        else
        {
          *(_DWORD *)(v10 + 312) = 1;
        }
      }
      else
      {
        v8 = -2147024809;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 88));
      goto LABEL_37;
    }
  }
  if ( !v12 )
    goto LABEL_7;
  v8 = CDRMClient::DeleteLicense(v12, wszLicenseId);
LABEL_37:
  if ( _InterlockedExchangeAdd(v7 + 4, 0xFFFFFFFF) == 1 )
    operator delete((void *)v7);
LABEL_40:
  _RTLTRACE("[msdrm]:-DRMDeleteLicense HR=%x\n", v8);
  return v8;
}

```

## disassembly

```asm
0x18001b800  mov     [rsp+arg_8], rbx
0x18001b805  mov     [rsp+arg_18], rbp
0x18001b80a  push    rsi
0x18001b80b  push    rdi
0x18001b80c  push    r14
0x18001b80e  sub     rsp, 40h
0x18001b812  mov     ebx, ecx
0x18001b814  mov     r14, rdx
0x18001b817  lea     rcx, aMsdrmDrmdelete; "[msdrm]:+DRMDeleteLicense wszLicenseId="...
0x18001b81e  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18001b823  test    ebx, ebx
0x18001b825  jz      loc_18001BA09
0x18001b82b  xor     edx, edx
0x18001b82d  mov     rcx, r14
0x18001b830  call    ??$DRMIsValidStringT@G@@YA_NPEBGPEA_K@Z; DRMIsValidStringT<ushort>(ushort const *,unsigned __int64 *)
0x18001b835  test    al, al
0x18001b837  jz      loc_18001BA09
0x18001b83d  mov     edx, ebx; unsigned int
0x18001b83f  mov     ecx, 1; unsigned int
0x18001b844  call    ?GetPointer@DRMCInt@@SAPEAXIK@Z; DRMCInt::GetPointer(uint,ulong)
0x18001b849  mov     rsi, rax
0x18001b84c  test    rax, rax
0x18001b84f  jnz     short loc_18001B85B
0x18001b851  mov     ebx, 80070006h
0x18001b856  jmp     loc_18001BA0E
0x18001b85b  mov     ecx, [rax]
0x18001b85d  sub     ecx, 2; this
0x18001b860  jz      loc_18001B966
0x18001b866  cmp     ecx, 1
0x18001b869  jz      short loc_18001B875
0x18001b86b  mov     ebx, 80070006h
0x18001b870  jmp     loc_18001B9F2
0x18001b875  lea     r8, [rsp+58h+Block]; struct DRMCInt **
0x18001b87a  mov     [rsp+58h+Block], 0
0x18001b883  mov     edx, ebx; unsigned int
0x18001b885  call    ?Get@CHandleTable@@QEAAJKPEAPEAUDRMCInt@@@Z; CHandleTable::Get(ulong,DRMCInt * *)
0x18001b88a  test    eax, eax
0x18001b88c  jns     short loc_18001B892
0x18001b88e  xor     edi, edi
0x18001b890  jmp     short loc_18001B8C9
0x18001b892  mov     rbx, [rsp+58h+Block]
0x18001b897  test    rbx, rbx
0x18001b89a  jz      short loc_18001B88E
0x18001b89c  xor     edi, edi
0x18001b89e  cmp     dword ptr [rbx], 3
0x18001b8a1  jnz     short loc_18001B8B4
0x18001b8a3  mov     rcx, [rbx+8]; this
0x18001b8a7  call    ?IsInitialized@CDRMReader@@QEAAJXZ; CDRMReader::IsInitialized(void)
0x18001b8ac  test    eax, eax
0x18001b8ae  js      short loc_18001B8B4
0x18001b8b0  mov     rdi, [rbx+8]
0x18001b8b4  or      eax, 0FFFFFFFFh
0x18001b8b7  lock xadd [rbx+10h], eax
0x18001b8bc  cmp     eax, 1
0x18001b8bf  jnz     short loc_18001B8C9
0x18001b8c1  mov     rcx, rbx; Block
0x18001b8c4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001b8c9  xor     ebx, ebx
0x18001b8cb  test    rdi, rdi
0x18001b8ce  jz      loc_18001B9DC
0x18001b8d4  lea     rcx, [rdi+58h]; lpCriticalSection
0x18001b8d8  call    cs:__imp_EnterCriticalSection
0x18001b8de  mov     rax, [rdi+0B0h]
0x18001b8e5  mov     [rsp+58h+var_28], rax
0x18001b8ea  mov     rax, [rdi+0B8h]
0x18001b8f1  mov     [rsp+58h+var_20], rax
0x18001b8f6  test    r14, r14
0x18001b8f9  jnz     short loc_18001B902
0x18001b8fb  mov     ebx, 80070057h
0x18001b900  jmp     short loc_18001B957
0x18001b902  xor     edx, edx
0x18001b904  mov     [rsp+58h+var_38], r14
0x18001b909  lea     r9, [rsp+58h+var_28]
0x18001b90e  lea     ecx, [rdx+2]
0x18001b911  mov     r8d, ecx
0x18001b914  call    ?DeletePersistedLicense@@YAJW4DRM_LICENSE_TYPE@@HIPEAPEAGPEAG@Z; DeletePersistedLicense(DRM_LICENSE_TYPE,int,uint,ushort * *,ushort *)
0x18001b919  mov     ebx, eax
0x18001b91b  test    eax, eax
0x18001b91d  jnz     short loc_18001B92B
0x18001b91f  mov     dword ptr [rdi+138h], 1
0x18001b929  jmp     short loc_18001B957
0x18001b92b  cmp     eax, 8004CF3Ah
0x18001b930  jnz     short loc_18001B957
0x18001b932  xor     edx, edx
0x18001b934  mov     [rsp+58h+var_38], r14
0x18001b939  xor     r9d, r9d
0x18001b93c  xor     r8d, r8d
0x18001b93f  lea     ecx, [rdx+4]
0x18001b942  call    ?DeletePersistedLicense@@YAJW4DRM_LICENSE_TYPE@@HIPEAPEAGPEAG@Z; DeletePersistedLicense(DRM_LICENSE_TYPE,int,uint,ushort * *,ushort *)
0x18001b947  mov     ebx, eax
0x18001b949  test    eax, eax
0x18001b94b  jnz     short loc_18001B957
0x18001b94d  mov     dword ptr [rdi+13Ch], 1
0x18001b957  lea     rcx, [rdi+58h]; lpCriticalSection
0x18001b95b  call    cs:__imp_LeaveCriticalSection
0x18001b961  jmp     loc_18001B9F2
0x18001b966  lea     r8, [rsp+58h+Block]; struct DRMCInt **
0x18001b96b  mov     [rsp+58h+Block], 0
0x18001b974  mov     edx, ebx; unsigned int
0x18001b976  call    ?Get@CHandleTable@@QEAAJKPEAPEAUDRMCInt@@@Z; CHandleTable::Get(ulong,DRMCInt * *)
0x18001b97b  test    eax, eax
0x18001b97d  jns     short loc_18001B983
0x18001b97f  xor     ebx, ebx
0x18001b981  jmp     short loc_18001B9DC
0x18001b983  mov     rdi, [rsp+58h+Block]
0x18001b988  test    rdi, rdi
0x18001b98b  jz      short loc_18001B97F
0x18001b98d  cmp     dword ptr [rdi], 2
0x18001b990  jz      short loc_18001B996
0x18001b992  xor     ebx, ebx
0x18001b994  jmp     short loc_18001B9C7
0x18001b996  mov     rbx, [rdi+8]
0x18001b99a  lea     rbp, [rbx+58h]
0x18001b99e  mov     rcx, rbp; lpCriticalSection
0x18001b9a1  call    cs:__imp_EnterCriticalSection
0x18001b9a7  cmp     dword ptr [rbx+88h], 0FFFFFFFFh
0x18001b9ae  mov     rcx, rbp; lpCriticalSection
0x18001b9b1  jnz     short loc_18001B9BD
0x18001b9b3  xor     ebx, ebx
0x18001b9b5  call    cs:__imp_LeaveCriticalSection
0x18001b9bb  jmp     short loc_18001B9C7
0x18001b9bd  call    cs:__imp_LeaveCriticalSection
0x18001b9c3  mov     rbx, [rdi+8]
0x18001b9c7  or      eax, 0FFFFFFFFh
0x18001b9ca  lock xadd [rdi+10h], eax
0x18001b9cf  cmp     eax, 1
0x18001b9d2  jnz     short loc_18001B9DC
0x18001b9d4  mov     rcx, rdi; Block
0x18001b9d7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001b9dc  test    rbx, rbx
0x18001b9df  jz      loc_18001B86B
0x18001b9e5  mov     rdx, r14; unsigned __int16 *
0x18001b9e8  mov     rcx, rbx; this
0x18001b9eb  call    ?DeleteLicense@CDRMClient@@QEAAJPEAG@Z; CDRMClient::DeleteLicense(ushort *)
0x18001b9f0  mov     ebx, eax
0x18001b9f2  or      edx, 0FFFFFFFFh
0x18001b9f5  lock xadd [rsi+10h], edx
0x18001b9fa  cmp     edx, 1
0x18001b9fd  jnz     short loc_18001BA0E
0x18001b9ff  mov     rcx, rsi; Block
0x18001ba02  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001ba07  jmp     short loc_18001BA0E
0x18001ba09  mov     ebx, 80070057h
0x18001ba0e  mov     edx, ebx
0x18001ba10  lea     rcx, aMsdrmDrmdelete_0; "[msdrm]:-DRMDeleteLicense HR=%x\n"
0x18001ba17  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18001ba1c  mov     rbp, [rsp+58h+arg_18]
0x18001ba21  mov     eax, ebx
0x18001ba23  mov     rbx, [rsp+58h+arg_8]
0x18001ba28  add     rsp, 40h
0x18001ba2c  pop     r14
0x18001ba2e  pop     rdi
0x18001ba2f  pop     rsi
0x18001ba30  retn
```
