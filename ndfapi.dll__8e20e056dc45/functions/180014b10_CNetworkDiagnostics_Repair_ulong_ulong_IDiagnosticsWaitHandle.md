# CNetworkDiagnostics::Repair(ulong,ulong,IDiagnosticsWaitHandle * *)

- ea: `0x180014b10`
- end: `0x180014c7b`
- name: `?Repair@CNetworkDiagnostics@@UEAAJKKPEAPEAUIDiagnosticsWaitHandle@@@Z`
- size: `363`
- prototype: `__int64 __fastcall(CNetworkDiagnostics *this, int, int, struct IDiagnosticsWaitHandle **)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180012384`
- `0x180014b10`
- `0x180014e20`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180014b37`
- `KERNEL32!EnterCriticalSection` at `0x180014b37`
- `KERNEL32!LeaveCriticalSection` at `0x180014b63`
- `KERNEL32!LeaveCriticalSection` at `0x180014bb7`
- `KERNEL32!LeaveCriticalSection` at `0x180014c29`
- `KERNEL32!LeaveCriticalSection` at `0x180014c6e`
- `KERNEL32!LeaveCriticalSection` at `0x180014b63`
- `KERNEL32!LeaveCriticalSection` at `0x180014bb7`
- `KERNEL32!LeaveCriticalSection` at `0x180014c29`
- `KERNEL32!LeaveCriticalSection` at `0x180014c6e`
- `KERNEL32!CreateThread` at `0x180014c18`
- `KERNEL32!CreateThread` at `0x180014c18`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CNetworkDiagnostics::Repair(
        CNetworkDiagnostics *this,
        int a2,
        int a3,
        struct IDiagnosticsWaitHandle **a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  int v9; // esi
  _QWORD *v10; // r14
  __int64 v12; // r11
  unsigned int v13; // edx
  unsigned __int64 v14; // rax
  unsigned int v15; // r8d
  __int64 v16; // r10
  HANDLE Thread; // rax
  __int64 v18; // rdx
  __int64 v19; // rcx
  int v20; // edi
  __int64 v21; // [rsp+80h] [rbp+8h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 128);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  if ( *((int *)this + 30) < 3 )
  {
    v9 = -2147024120;
LABEL_4:
    LeaveCriticalSection(v4);
    return (unsigned int)v9;
  }
  v10 = (_QWORD *)((char *)this + 40);
  v9 = ResetWaitHandle((void **)this + 5);
  if ( v9 < 0 )
    goto LABEL_4;
  v12 = *((_QWORD *)this + 3);
  v13 = 0;
  if ( !*((_DWORD *)this + 8) )
    goto LABEL_11;
  while ( 1 )
  {
    v14 = (unsigned __int64)v13 << 6;
    if ( *(_WORD *)(v14 + v12 + 56) )
      break;
LABEL_10:
    if ( ++v13 >= *((_DWORD *)this + 8) )
      goto LABEL_11;
  }
  v15 = 0;
  while ( 1 )
  {
    v16 = *(_QWORD *)(v14 + v12 + 48) + 120LL * v15;
    if ( *(unsigned __int16 *)(v16 + 112) == a2 )
      break;
    if ( ++v15 >= *(unsigned __int16 *)(v14 + v12 + 56) )
      goto LABEL_10;
  }
  if ( v16 )
  {
    *((_DWORD *)this + 19) = 0;
    *((_QWORD *)this + 13) = 0;
    *((_QWORD *)this + 14) = 0;
    *((_QWORD *)this + 8) = *((_QWORD *)this + 2);
    *((_QWORD *)this + 10) = (char *)this + 52;
    *((_DWORD *)this + 18) = a3;
    *((_QWORD *)this + 12) = v16;
    *((_QWORD *)this + 11) = (char *)this + 120;
    Thread = CreateThread(0, 0, RepairThread, (char *)this + 64, 0, 0);
    *v10 = Thread;
    if ( Thread )
    {
      v21 = 0;
      v20 = ATL::CComCreator<ATL::CComObject<CIDiagnosticsWaitHandle>>::CreateInstance(v19, v18, &v21);
      if ( v20 >= 0 )
      {
        *(_QWORD *)(v21 + 72) = *v10;
        *a4 = (struct IDiagnosticsWaitHandle *)v21;
      }
      LeaveCriticalSection(v4);
      return (unsigned int)v20;
    }
    else
    {
      LeaveCriticalSection(v4);
      return 2147943454LL;
    }
  }
  else
  {
LABEL_11:
    LeaveCriticalSection(v4);
    return 2147943568LL;
  }
}

```

## disassembly

```asm
0x180014b10  push    rbx
0x180014b12  push    rbp
0x180014b13  push    rsi
0x180014b14  push    rdi
0x180014b15  push    r12
0x180014b17  push    r13
0x180014b19  push    r14
0x180014b1b  push    r15
0x180014b1d  sub     rsp, 38h
0x180014b21  lea     rbx, [rcx+80h]
0x180014b28  mov     rdi, rcx
0x180014b2b  mov     rcx, rbx; lpCriticalSection
0x180014b2e  mov     r15, r9
0x180014b31  mov     r13d, r8d
0x180014b34  mov     r12d, edx
0x180014b37  call    cs:__imp_EnterCriticalSection
0x180014b3d  lea     rbp, [rdi+78h]
0x180014b41  cmp     dword ptr [rbp+0], 3
0x180014b45  jge     short loc_180014B4E
0x180014b47  mov     esi, 80070308h
0x180014b4c  jmp     short loc_180014B60
0x180014b4e  lea     r14, [rdi+28h]
0x180014b52  mov     rcx, r14; void **
0x180014b55  call    ?ResetWaitHandle@@YAJPEAPEAX@Z; ResetWaitHandle(void * *)
0x180014b5a  mov     esi, eax
0x180014b5c  test    eax, eax
0x180014b5e  jns     short loc_180014B6D
0x180014b60  mov     rcx, rbx; lpCriticalSection
0x180014b63  call    cs:__imp_LeaveCriticalSection
0x180014b69  mov     eax, esi
0x180014b6b  jmp     short loc_180014BC2
0x180014b6d  mov     r11, [rdi+18h]
0x180014b71  xor     edx, edx
0x180014b73  cmp     [rdi+20h], edx
0x180014b76  jbe     short loc_180014BB4
0x180014b78  mov     eax, edx
0x180014b7a  shl     rax, 6
0x180014b7e  movzx   r9d, word ptr [rax+r11+38h]
0x180014b84  test    r9d, r9d
0x180014b87  jz      short loc_180014BAD
0x180014b89  mov     rsi, [rax+r11+30h]
0x180014b8e  xor     r8d, r8d
0x180014b91  mov     eax, r8d
0x180014b94  imul    r10, rax, 78h ; 'x'
0x180014b98  add     r10, rsi
0x180014b9b  movzx   eax, word ptr [r10+70h]
0x180014ba0  cmp     eax, r12d
0x180014ba3  jz      short loc_180014BD3
0x180014ba5  inc     r8d
0x180014ba8  cmp     r8d, r9d
0x180014bab  jb      short loc_180014B91
0x180014bad  inc     edx
0x180014baf  cmp     edx, [rdi+20h]
0x180014bb2  jb      short loc_180014B78
0x180014bb4  mov     rcx, rbx; lpCriticalSection
0x180014bb7  call    cs:__imp_LeaveCriticalSection
0x180014bbd  mov     eax, 80070490h
0x180014bc2  add     rsp, 38h
0x180014bc6  pop     r15
0x180014bc8  pop     r14
0x180014bca  pop     r13
0x180014bcc  pop     r12
0x180014bce  pop     rdi
0x180014bcf  pop     rsi
0x180014bd0  pop     rbp
0x180014bd1  pop     rbx
0x180014bd2  retn
0x180014bd3  xor     esi, esi
0x180014bd5  test    r10, r10
0x180014bd8  jz      short loc_180014BB4
0x180014bda  mov     [rdi+4Ch], esi
0x180014bdd  lea     r9, [rdi+40h]; lpParameter
0x180014be1  mov     [rdi+68h], rsi
0x180014be5  lea     r8, ?RepairThread@@YAKPEAX@Z; lpStartAddress
0x180014bec  mov     [rdi+70h], rsi
0x180014bf0  xor     edx, edx; dwStackSize
0x180014bf2  mov     rax, [rdi+10h]
0x180014bf6  xor     ecx, ecx; lpThreadAttributes
0x180014bf8  mov     [r9], rax
0x180014bfb  lea     rax, [rdi+34h]
0x180014bff  mov     [rsp+78h+lpThreadId], rsi; lpThreadId
0x180014c04  mov     [rdi+50h], rax
0x180014c08  mov     [rdi+48h], r13d
0x180014c0c  mov     [rdi+60h], r10
0x180014c10  mov     [rdi+58h], rbp
0x180014c14  mov     [rsp+78h+dwCreationFlags], esi; dwCreationFlags
0x180014c18  call    cs:__imp_CreateThread
0x180014c1e  mov     [r14], rax
0x180014c21  test    rax, rax
0x180014c24  jnz     short loc_180014C36
0x180014c26  mov     rcx, rbx; lpCriticalSection
0x180014c29  call    cs:__imp_LeaveCriticalSection
0x180014c2f  mov     eax, 8007041Eh
0x180014c34  jmp     short loc_180014BC2
0x180014c36  lea     r8, [rsp+78h+arg_0]
0x180014c3e  mov     [rsp+78h+arg_0], rsi
0x180014c46  call    ?CreateInstance@?$CComCreator@V?$CComObject@VCIDiagnosticsWaitHandle@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CIDiagnosticsWaitHandle>>::CreateInstance(void *,_GUID const &,void * *)
0x180014c4b  mov     edi, eax
0x180014c4d  test    eax, eax
0x180014c4f  js      short loc_180014C6B
0x180014c51  mov     rcx, [rsp+78h+arg_0]
0x180014c59  mov     rdx, [r14]
0x180014c5c  mov     [rcx+48h], rdx
0x180014c60  mov     rcx, [rsp+78h+arg_0]
0x180014c68  mov     [r15], rcx
0x180014c6b  mov     rcx, rbx; lpCriticalSection
0x180014c6e  call    cs:__imp_LeaveCriticalSection
0x180014c74  mov     eax, edi
0x180014c76  jmp     loc_180014BC2
```
