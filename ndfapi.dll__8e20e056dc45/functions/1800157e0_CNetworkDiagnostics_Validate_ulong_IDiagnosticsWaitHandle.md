# CNetworkDiagnostics::Validate(ulong,IDiagnosticsWaitHandle * *)

- ea: `0x1800157e0`
- end: `0x1800158f3`
- name: `?Validate@CNetworkDiagnostics@@UEAAJKPEAPEAUIDiagnosticsWaitHandle@@@Z`
- size: `275`
- prototype: `__int64 __fastcall(CNetworkDiagnostics *__hidden this, unsigned int, struct IDiagnosticsWaitHandle **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180012384`
- `0x180014e20`
- `0x1800157e0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180015809`
- `KERNEL32!EnterCriticalSection` at `0x180015809`
- `KERNEL32!LeaveCriticalSection` at `0x1800158d4`
- `KERNEL32!LeaveCriticalSection` at `0x1800158d4`
- `KERNEL32!CreateThread` at `0x18001588f`
- `KERNEL32!CreateThread` at `0x18001588f`

## pseudocode

```c
__int64 __fastcall CNetworkDiagnostics::Validate(void **this, int a2, struct IDiagnosticsWaitHandle **a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rbp
  int v7; // ebx
  _QWORD *v8; // rsi
  HANDLE Thread; // rax
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v13; // [rsp+60h] [rbp+8h] BYREF

  v3 = (struct _RTL_CRITICAL_SECTION *)(this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 16));
  if ( *((_DWORD *)this + 30) == 5 )
  {
    v8 = this + 5;
    v7 = ResetWaitHandle(this + 5);
    if ( v7 >= 0 )
    {
      *((_DWORD *)this + 19) = 0;
      this[12] = 0;
      this[13] = 0;
      this[14] = 0;
      this[8] = this[2];
      this[10] = this + 7;
      *((_DWORD *)this + 18) = a2;
      this[11] = this + 15;
      Thread = CreateThread(0, 0, ValidateThread, this + 8, 0, 0);
      *v8 = Thread;
      if ( Thread )
      {
        v13 = 0;
        v7 = ATL::CComCreator<ATL::CComObject<CIDiagnosticsWaitHandle>>::CreateInstance(v11, v10, &v13);
        if ( v7 >= 0 )
        {
          *(_QWORD *)(v13 + 72) = *v8;
          *a3 = (struct IDiagnosticsWaitHandle *)v13;
        }
      }
      else
      {
        v7 = -2147023842;
      }
    }
  }
  else
  {
    v7 = -2147024120;
  }
  LeaveCriticalSection(v3);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800157e0  mov     [rsp+arg_8], rbx
0x1800157e5  mov     [rsp+arg_10], rbp
0x1800157ea  push    rsi
0x1800157eb  push    rdi
0x1800157ec  push    r12
0x1800157ee  push    r14
0x1800157f0  push    r15
0x1800157f2  sub     rsp, 30h
0x1800157f6  lea     rbp, [rcx+80h]
0x1800157fd  mov     rdi, rcx
0x180015800  mov     rcx, rbp; lpCriticalSection
0x180015803  mov     r15, r8
0x180015806  mov     r12d, edx
0x180015809  call    cs:__imp_EnterCriticalSection
0x18001580f  lea     r14, [rdi+78h]
0x180015813  cmp     dword ptr [r14], 5
0x180015817  jz      short loc_180015823
0x180015819  mov     ebx, 80070308h
0x18001581e  jmp     loc_1800158D1
0x180015823  lea     rsi, [rdi+28h]
0x180015827  mov     rcx, rsi; void **
0x18001582a  call    ?ResetWaitHandle@@YAJPEAPEAX@Z; ResetWaitHandle(void * *)
0x18001582f  mov     ebx, eax
0x180015831  test    eax, eax
0x180015833  js      loc_1800158D1
0x180015839  mov     dword ptr [rdi+4Ch], 0
0x180015840  lea     r9, [rdi+40h]; lpParameter
0x180015844  mov     qword ptr [rdi+60h], 0
0x18001584c  lea     r8, ?ValidateThread@@YAKPEAX@Z; lpStartAddress
0x180015853  mov     qword ptr [rdi+68h], 0
0x18001585b  xor     edx, edx; dwStackSize
0x18001585d  mov     qword ptr [rdi+70h], 0
0x180015865  xor     ecx, ecx; lpThreadAttributes
0x180015867  mov     rax, [rdi+10h]
0x18001586b  mov     [r9], rax
0x18001586e  lea     rax, [rdi+38h]
0x180015872  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x18001587b  mov     [rdi+50h], rax
0x18001587f  mov     [rdi+48h], r12d
0x180015883  mov     [rdi+58h], r14
0x180015887  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x18001588f  call    cs:__imp_CreateThread
0x180015895  mov     [rsi], rax
0x180015898  test    rax, rax
0x18001589b  jnz     short loc_1800158A4
0x18001589d  mov     ebx, 8007041Eh
0x1800158a2  jmp     short loc_1800158D1
0x1800158a4  lea     r8, [rsp+58h+arg_0]
0x1800158a9  mov     [rsp+58h+arg_0], 0
0x1800158b2  call    ?CreateInstance@?$CComCreator@V?$CComObject@VCIDiagnosticsWaitHandle@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CIDiagnosticsWaitHandle>>::CreateInstance(void *,_GUID const &,void * *)
0x1800158b7  mov     ebx, eax
0x1800158b9  test    eax, eax
0x1800158bb  js      short loc_1800158D1
0x1800158bd  mov     rax, [rsp+58h+arg_0]
0x1800158c2  mov     rdx, [rsi]
0x1800158c5  mov     [rax+48h], rdx
0x1800158c9  mov     rax, [rsp+58h+arg_0]
0x1800158ce  mov     [r15], rax
0x1800158d1  mov     rcx, rbp; lpCriticalSection
0x1800158d4  call    cs:__imp_LeaveCriticalSection
0x1800158da  mov     rbp, [rsp+58h+arg_10]
0x1800158df  mov     eax, ebx
0x1800158e1  mov     rbx, [rsp+58h+arg_8]
0x1800158e6  add     rsp, 30h
0x1800158ea  pop     r15
0x1800158ec  pop     r14
0x1800158ee  pop     r12
0x1800158f0  pop     rdi
0x1800158f1  pop     rsi
0x1800158f2  retn
```
