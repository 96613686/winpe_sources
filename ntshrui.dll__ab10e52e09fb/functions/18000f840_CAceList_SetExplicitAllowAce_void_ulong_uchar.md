# CAceList::SetExplicitAllowAce(void *,ulong,uchar)

- ea: `0x18000f840`
- end: `0x18000faf7`
- name: `?SetExplicitAllowAce@CAceList@@QEAAJPEAXKE@Z`
- size: `695`
- prototype: `int(CAceList *__hidden this, void *, unsigned int, unsigned __int8)`
- caller_count: `7`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180009c50`
- `0x180055420`
- `0x180059018`
- `0x180059470`
- `0x180059a80`
- `0x18005a6d8`
- `0x18005c584`

## callees

- `0x1800098dc`
- `0x18000f4b0`
- `0x18000f7a0`
- `0x18000f7f0`
- `0x18000f840`
- `0x1800259bc`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fa87`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fa87`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000f944`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000f944`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000f8d0`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000f8d0`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000f9a5`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000f9a5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000f92b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000f97a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000f92b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000f97a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f98d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f98d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fabd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fabd`
- `ntdll!RtlMapGenericMask` at `0x18000f9e0`
- `ntdll!RtlMapGenericMask` at `0x18000f9e0`

## pseudocode

```c
__int64 __fastcall CAceList::SetExplicitAllowAce(CAceList *this, void *a2, int a3, char a4)
{
  int *v4; // rdi
  int v9; // edi
  FARPROC ProcAddress; // rax
  int i; // ebx
  __int64 v12; // rbp
  __int64 v13; // rbp
  unsigned int v14; // ebp
  _QWORD *v15; // rax
  unsigned int v16; // edx
  _QWORD *v17; // rbx
  __int16 LengthSid; // ax
  __int16 v19; // r13
  int Error; // edi
  __int64 result; // rax
  HLOCAL v22; // rax
  void *v23; // r12
  char v24; // cl
  unsigned int v25; // eax
  unsigned int (__fastcall *v26)(__int64, __int64, _QWORD *); // rax
  __int64 v27; // rdi
  DWORD nDestinationSidLength; // [rsp+60h] [rbp+8h]

  v4 = (int *)*((_QWORD *)this + 1);
  if ( v4 )
    v9 = *v4;
  else
    v9 = 0;
  ProcAddress = (FARPROC)qword_180095A20;
  for ( i = 0; ; ++i )
  {
    if ( i >= v9 )
    {
      v14 = -2147024882;
      v15 = operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
      v17 = v15;
      if ( !v15 )
        return v14;
      *v15 = 0x80000;
      v15[1] = 0;
      v15[2] = 0;
      v15[3] = 0;
      if ( !a2 )
      {
        v14 = -2147024809;
        goto LABEL_19;
      }
      LengthSid = GetLengthSid(a2);
      v17[1] = 0;
      v19 = LengthSid;
      Error = -2147024809;
      if ( IsValidSid(a2) )
      {
        nDestinationSidLength = GetLengthSid(a2);
        Error = -2147024882;
        v22 = LocalAlloc(0x40u, nDestinationSidLength);
        v23 = v22;
        if ( v22 )
        {
          if ( CopySid(nDestinationSidLength, v22, a2) )
          {
            Error = 0;
          }
          else
          {
            Error = ResultFromKnownLastError();
            if ( Error < 0 )
            {
              LocalFree(v23);
              goto LABEL_18;
            }
          }
          v17[1] = v23;
          *((_BYTE *)v17 + 1) = a4;
          *((_DWORD *)v17 + 1) = a3;
          *(_BYTE *)v17 = 0;
          *((_WORD *)v17 + 1) = v19 + 8;
          RtlMapGenericMask((PACCESS_MASK)v17 + 1, (PGENERIC_MAPPING)&GenericMapping);
          v24 = *(_BYTE *)v17;
          v25 = 0x80000000;
          *((_DWORD *)v17 + 7) = 0x80000000;
          if ( !v24 || v24 == 9 )
          {
            v25 = -2147483647;
            *((_DWORD *)v17 + 7) = -2147483647;
          }
          if ( (*((_BYTE *)v17 + 1) & 0x10) != 0 )
          {
            *((_DWORD *)v17 + 7) = v25 | 0x20;
LABEL_28:
            v26 = (unsigned int (__fastcall *)(__int64, __int64, _QWORD *))qword_1800959F8;
            v27 = *((_QWORD *)this + 1);
            if ( qword_1800959F8 == -1 )
            {
              GetProcFromComCtl32(&qword_1800959F8, 334);
              v26 = (unsigned int (__fastcall *)(__int64, __int64, _QWORD *))qword_1800959F8;
            }
            if ( v26 && v26(v27, 0x7FFFFFFF, v17) != -1 )
              return 0;
            if ( !v17 )
              return v14;
LABEL_19:
            CAce::`scalar deleting destructor'((CAce *)v17, v16);
            return v14;
          }
        }
      }
      if ( Error >= 0 )
        goto LABEL_28;
LABEL_18:
      v14 = Error;
      goto LABEL_19;
    }
    v12 = *((_QWORD *)this + 1);
    if ( ProcAddress == (FARPROC)-1LL )
    {
      if ( !g_hinstCC )
      {
        DelayLoadCC();
        if ( !g_hinstCC )
        {
          ProcAddress = 0;
          qword_180095A20 = 0;
LABEL_42:
          v13 = 0;
          goto LABEL_8;
        }
      }
      ProcAddress = GetProcAddress(g_hinstCC, (LPCSTR)0x14C);
      qword_180095A20 = (__int64 (__fastcall *)(_QWORD, _QWORD))ProcAddress;
    }
    if ( !ProcAddress )
      goto LABEL_42;
    v13 = ((__int64 (__fastcall *)(__int64, _QWORD))ProcAddress)(v12, i);
    ProcAddress = (FARPROC)qword_180095A20;
LABEL_8:
    if ( !*(_DWORD *)(v13 + 24) && (a4 == -1 || *(_BYTE *)(v13 + 1) == a4) )
      break;
LABEL_13:
    ;
  }
  if ( !EqualSid(*(PSID *)(v13 + 8), a2) )
  {
    ProcAddress = (FARPROC)qword_180095A20;
    goto LABEL_13;
  }
  result = 0;
  *(_DWORD *)(v13 + 4) = a3;
  return result;
}

```

## disassembly

```asm
0x18000f840  mov     [rsp+arg_18], r9b
0x18000f845  mov     [rsp+arg_10], r8d
0x18000f84a  push    rbx
0x18000f84b  push    rsi
0x18000f84c  push    rdi
0x18000f84d  push    r12
0x18000f84f  push    r13
0x18000f851  push    r14
0x18000f853  push    r15
0x18000f855  sub     rsp, 20h
0x18000f859  mov     rdi, [rcx+8]
0x18000f85d  xor     r13d, r13d
0x18000f860  movzx   r14d, r9b
0x18000f864  mov     r12d, r8d
0x18000f867  mov     rsi, rdx
0x18000f86a  mov     r15, rcx
0x18000f86d  test    rdi, rdi
0x18000f870  jz      loc_18000FAD2
0x18000f876  mov     edi, [rdi]
0x18000f878  mov     rax, cs:qword_180095A20
0x18000f87f  mov     ebx, r13d
0x18000f882  mov     [rsp+58h+arg_8], rbp
0x18000f887  cmp     ebx, edi
0x18000f889  jge     short loc_18000F8E9
0x18000f88b  mov     rbp, [r15+8]
0x18000f88f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000f893  jz      loc_18000FA64
0x18000f899  test    rax, rax
0x18000f89c  jz      loc_18000FAA3
0x18000f8a2  movsxd  rdx, ebx
0x18000f8a5  mov     rcx, rbp
0x18000f8a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8ad  mov     rbp, rax
0x18000f8b0  mov     rax, cs:qword_180095A20
0x18000f8b7  cmp     [rbp+18h], r13d
0x18000f8bb  jnz     short loc_18000F8E5
0x18000f8bd  cmp     r14b, 0FFh
0x18000f8c1  jz      short loc_18000F8C9
0x18000f8c3  cmp     [rbp+1], r14b
0x18000f8c7  jnz     short loc_18000F8E5
0x18000f8c9  mov     rcx, [rbp+8]; pSid1
0x18000f8cd  mov     rdx, rsi; pSid2
0x18000f8d0  call    cs:__imp_EqualSid
0x18000f8d6  test    eax, eax
0x18000f8d8  jnz     loc_18000FA58
0x18000f8de  mov     rax, cs:qword_180095A20
0x18000f8e5  inc     ebx
0x18000f8e7  jmp     short loc_18000F887
0x18000f8e9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f8f0  mov     ecx, 20h ; ' '; unsigned __int64
0x18000f8f5  mov     ebp, 8007000Eh
0x18000f8fa  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000f8ff  mov     qword ptr [rsp+58h+nDestinationSidLength], rax
0x18000f904  mov     rbx, rax
0x18000f907  test    rax, rax
0x18000f90a  jz      short loc_18000F960
0x18000f90c  mov     qword ptr [rax], 80000h
0x18000f913  mov     [rax+8], r13
0x18000f917  mov     [rax+10h], r13
0x18000f91b  mov     [rax+18h], r13
0x18000f91f  test    rsi, rsi
0x18000f922  jz      loc_18000FAC8
0x18000f928  mov     rcx, rsi; pSid
0x18000f92b  call    cs:__imp_GetLengthSid
0x18000f931  mov     rcx, rsi; pSid
0x18000f934  mov     qword ptr [rbx+8], 0
0x18000f93c  mov     r13d, eax
0x18000f93f  mov     edi, 80070057h
0x18000f944  call    cs:__imp_IsValidSid
0x18000f94a  test    eax, eax
0x18000f94c  jnz     short loc_18000F977
0x18000f94e  test    edi, edi
0x18000f950  jns     loc_18000FA0D
0x18000f956  mov     ebp, edi
0x18000f958  mov     rcx, rbx; this
0x18000f95b  call    ??_GCAce@@QEAAPEAXI@Z; CAce::`scalar deleting destructor'(uint)
0x18000f960  mov     eax, ebp
0x18000f962  mov     rbp, [rsp+58h+arg_8]
0x18000f967  add     rsp, 20h
0x18000f96b  pop     r15
0x18000f96d  pop     r14
0x18000f96f  pop     r13
0x18000f971  pop     r12
0x18000f973  pop     rdi
0x18000f974  pop     rsi
0x18000f975  pop     rbx
0x18000f976  retn
0x18000f977  mov     rcx, rsi; pSid
0x18000f97a  call    cs:__imp_GetLengthSid
0x18000f980  mov     edx, eax; uBytes
0x18000f982  mov     ecx, 40h ; '@'; uFlags
0x18000f987  mov     [rsp+58h+nDestinationSidLength], eax
0x18000f98b  mov     edi, ebp
0x18000f98d  call    cs:__imp_LocalAlloc
0x18000f993  mov     r12, rax
0x18000f996  test    rax, rax
0x18000f999  jz      short loc_18000F94E
0x18000f99b  mov     ecx, [rsp+58h+nDestinationSidLength]; nDestinationSidLength
0x18000f99f  mov     r8, rsi; pSourceSid
0x18000f9a2  mov     rdx, rax; pDestinationSid
0x18000f9a5  call    cs:__imp_CopySid
0x18000f9ab  test    eax, eax
0x18000f9ad  jz      loc_18000FAAB
0x18000f9b3  xor     edi, edi
0x18000f9b5  movzx   eax, [rsp+58h+arg_18]
0x18000f9ba  lea     rdx, GenericMapping; GenericMapping
0x18000f9c1  mov     [rbx+8], r12
0x18000f9c5  lea     rcx, [rbx+4]; AccessMask
0x18000f9c9  mov     [rbx+1], al
0x18000f9cc  add     r13w, 8
0x18000f9d1  mov     eax, [rsp+58h+arg_10]
0x18000f9d5  mov     [rbx+4], eax
0x18000f9d8  mov     byte ptr [rbx], 0
0x18000f9db  mov     [rbx+2], r13w
0x18000f9e0  call    cs:__imp_RtlMapGenericMask
0x18000f9e6  movzx   ecx, byte ptr [rbx]
0x18000f9e9  mov     eax, 80000000h
0x18000f9ee  mov     [rbx+1Ch], eax
0x18000f9f1  test    cl, cl
0x18000f9f3  jnz     short loc_18000FA51
0x18000f9f5  mov     eax, 80000001h
0x18000f9fa  mov     [rbx+1Ch], eax
0x18000f9fd  test    byte ptr [rbx+1], 10h
0x18000fa01  jz      loc_18000F94E
0x18000fa07  or      eax, 20h
0x18000fa0a  mov     [rbx+1Ch], eax
0x18000fa0d  mov     rax, cs:qword_1800959F8
0x18000fa14  mov     rdi, [r15+8]
0x18000fa18  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000fa1c  jz      loc_18000FADA
0x18000fa22  test    rax, rax
0x18000fa25  jz      short loc_18000FA3C
0x18000fa27  mov     r8, rbx
0x18000fa2a  mov     edx, 7FFFFFFFh
0x18000fa2f  mov     rcx, rdi
0x18000fa32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa37  cmp     eax, 0FFFFFFFFh
0x18000fa3a  jnz     short loc_18000FA4A
0x18000fa3c  test    rbx, rbx
0x18000fa3f  jnz     loc_18000F958
0x18000fa45  jmp     loc_18000F960
0x18000fa4a  xor     eax, eax
0x18000fa4c  jmp     loc_18000F962
0x18000fa51  cmp     cl, 9
0x18000fa54  jnz     short loc_18000F9FD
0x18000fa56  jmp     short loc_18000F9F5
0x18000fa58  mov     eax, r13d
0x18000fa5b  mov     [rbp+4], r12d
0x18000fa5f  jmp     loc_18000F962
0x18000fa64  cmp     cs:g_hinstCC, r13
0x18000fa6b  jnz     short loc_18000FA7B
0x18000fa6d  call    DelayLoadCC
0x18000fa72  cmp     cs:g_hinstCC, r13
0x18000fa79  jz      short loc_18000FA99
0x18000fa7b  mov     rcx, cs:g_hinstCC; hModule
0x18000fa82  mov     edx, 14Ch; lpProcName
0x18000fa87  call    cs:__imp_GetProcAddress
0x18000fa8d  mov     cs:qword_180095A20, rax
0x18000fa94  jmp     loc_18000F899
0x18000fa99  mov     rax, r13
0x18000fa9c  mov     cs:qword_180095A20, rax
0x18000faa3  mov     rbp, r13
0x18000faa6  jmp     loc_18000F8B7
0x18000faab  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000fab0  mov     edi, eax
0x18000fab2  test    eax, eax
0x18000fab4  jns     loc_18000F9B5
0x18000faba  mov     rcx, r12; hMem
0x18000fabd  call    cs:__imp_LocalFree
0x18000fac3  jmp     loc_18000F956
0x18000fac8  mov     ebp, 80070057h
0x18000facd  jmp     loc_18000F958
0x18000fad2  mov     edi, r13d
0x18000fad5  jmp     loc_18000F878
0x18000fada  mov     edx, 14Eh
0x18000fadf  lea     rcx, qword_1800959F8
0x18000fae6  call    _GetProcFromComCtl32
0x18000faeb  mov     rax, cs:qword_1800959F8
0x18000faf2  jmp     loc_18000FA22
```
