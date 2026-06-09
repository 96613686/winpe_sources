# CWMWriter::GetCapabilities(ulong *)

- ea: `0x18000f970`
- end: `0x18000fa95`
- name: `?GetCapabilities@CWMWriter@@UEAAJPEAK@Z`
- size: `293`
- prototype: `__int64 __fastcall(CWMWriter *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001460`
- `0x18000f970`
- `0x18001f010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000f99b`
- `KERNEL32!EnterCriticalSection` at `0x18000f99b`
- `KERNEL32!LeaveCriticalSection` at `0x18000fa70`
- `KERNEL32!LeaveCriticalSection` at `0x18000fa70`

## pseudocode

```c
__int64 __fastcall CWMWriter::GetCapabilities(struct _RTL_CRITICAL_SECTION *this, unsigned int *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rsi
  __int64 v9; // [rsp+20h] [rbp-28h] BYREF
  __int64 v10; // [rsp+28h] [rbp-20h] BYREF

  v2 = this + 3;
  EnterCriticalSection(this + 3);
  *a2 = 0;
  if ( !LODWORD(this[4].DebugInfo) )
  {
    *a2 = 32;
    v5 = *(_QWORD *)&this[7].LockCount;
    if ( v5 )
    {
      do
      {
        v6 = *(_QWORD *)(v5 + 16);
        v7 = *(_QWORD *)(v5 + 8);
        if ( *(_QWORD *)(v6 + 48) )
        {
          v10 = 0;
          if ( !(*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)(v6 + 24) + 48LL))(v6 + 24, &v10) )
          {
            v9 = 0;
            if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v10)(v10, &IID_IMediaSeeking, &v9) >= 0 )
            {
              (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v9 + 32LL))(v9, a2);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
          }
        }
        v5 = v7;
      }
      while ( v7 );
    }
  }
  *a2 |= 8u;
  LeaveCriticalSection(v2);
  return 0;
}

```

## disassembly

```asm
0x18000f970  mov     [rsp+arg_10], rbx
0x18000f975  mov     [rsp+arg_18], rsi
0x18000f97a  push    rdi
0x18000f97b  sub     rsp, 40h
0x18000f97f  mov     rax, cs:__security_cookie
0x18000f986  xor     rax, rsp
0x18000f989  mov     [rsp+48h+var_18], rax
0x18000f98e  lea     rbx, [rcx+78h]
0x18000f992  mov     rsi, rcx
0x18000f995  mov     rcx, rbx; lpCriticalSection
0x18000f998  mov     rdi, rdx
0x18000f99b  call    cs:__imp_EnterCriticalSection
0x18000f9a1  mov     dword ptr [rdi], 0
0x18000f9a7  cmp     dword ptr [rsi+0A0h], 0
0x18000f9ae  jnz     loc_18000FA6A
0x18000f9b4  mov     dword ptr [rdi], 20h ; ' '
0x18000f9ba  mov     rax, [rsi+120h]
0x18000f9c1  test    rax, rax
0x18000f9c4  jz      loc_18000FA6A
0x18000f9ca  mov     rcx, [rax+10h]
0x18000f9ce  mov     rsi, [rax+8]
0x18000f9d2  cmp     qword ptr [rcx+30h], 0
0x18000f9d7  jz      loc_18000FA5E
0x18000f9dd  add     rcx, 18h
0x18000f9e1  mov     [rsp+48h+var_20], 0
0x18000f9ea  lea     rdx, [rsp+48h+var_20]
0x18000f9ef  mov     rax, [rcx]
0x18000f9f2  mov     rax, [rax+30h]
0x18000f9f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9fb  test    eax, eax
0x18000f9fd  jnz     short loc_18000FA5E
0x18000f9ff  mov     rcx, [rsp+48h+var_20]
0x18000fa04  lea     r8, [rsp+48h+var_28]
0x18000fa09  mov     [rsp+48h+var_28], 0
0x18000fa12  lea     rdx, IID_IMediaSeeking
0x18000fa19  mov     rax, [rcx]
0x18000fa1c  mov     rax, [rax]
0x18000fa1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa24  test    eax, eax
0x18000fa26  js      short loc_18000FA4D
0x18000fa28  mov     rcx, [rsp+48h+var_28]
0x18000fa2d  mov     rdx, rdi
0x18000fa30  mov     rax, [rcx]
0x18000fa33  mov     rax, [rax+20h]
0x18000fa37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa3c  mov     rcx, [rsp+48h+var_28]
0x18000fa41  mov     rax, [rcx]
0x18000fa44  mov     rax, [rax+10h]
0x18000fa48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa4d  mov     rcx, [rsp+48h+var_20]
0x18000fa52  mov     rax, [rcx]
0x18000fa55  mov     rax, [rax+10h]
0x18000fa59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa5e  mov     rax, rsi
0x18000fa61  test    rsi, rsi
0x18000fa64  jnz     loc_18000F9CA
0x18000fa6a  or      dword ptr [rdi], 8
0x18000fa6d  mov     rcx, rbx; lpCriticalSection
0x18000fa70  call    cs:__imp_LeaveCriticalSection
0x18000fa76  xor     eax, eax
0x18000fa78  mov     rcx, [rsp+48h+var_18]
0x18000fa7d  xor     rcx, rsp; StackCookie
0x18000fa80  call    __security_check_cookie
0x18000fa85  mov     rbx, [rsp+48h+arg_10]
0x18000fa8a  mov     rsi, [rsp+48h+arg_18]
0x18000fa8f  add     rsp, 40h
0x18000fa93  pop     rdi
0x18000fa94  retn
```
