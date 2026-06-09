# SipProvider::PutSignature(SIP_SUBJECTINFO_ const *,ulong,ulong *,ulong,uchar *)

- ea: `0x180004dd4`
- end: `0x180004eb7`
- name: `?PutSignature@SipProvider@@QEAAKPEBUSIP_SUBJECTINFO_@@KPEAKKPEAE@Z`
- size: `227`
- prototype: `unsigned int(SipProvider *__hidden this, const struct SIP_SUBJECTINFO_ *, unsigned int, unsigned int *, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180004ca0`

## callees

- `0x180004834`
- `0x180004dd4`
- `0x180006010`

## pseudocode

```c
__int64 __fastcall SipProvider::PutSignature(
        SipProvider *this,
        const struct SIP_SUBJECTINFO_ *a2,
        int a3,
        unsigned int *a4,
        unsigned int a5,
        unsigned __int8 *a6)
{
  SipFile *v9; // rax
  SipFile *v10; // rsi
  unsigned int v11; // ebx
  __int64 v12; // rdi
  int v13; // eax

  if ( a4 )
    *a4 = 0;
  v9 = (SipFile *)(*(__int64 (__fastcall **)(SipProvider *))(*(_QWORD *)this + 8LL))(this);
  v10 = v9;
  if ( v9 )
  {
    v12 = 0;
    v11 = SipFile::Open(v9, a2, 1u);
    if ( !v11 )
    {
      v12 = (*(__int64 (__fastcall **)(SipProvider *))(*(_QWORD *)this + 16LL))(this);
      if ( v12 )
      {
        v13 = *((_DWORD *)v10 + 14);
        *(_DWORD *)(v12 + 8) = a3;
        *(_DWORD *)(v12 + 28) = v13;
        if ( a6 && a5 )
        {
          *(_QWORD *)(v12 + 16) = a6;
          *(_DWORD *)(v12 + 12) = a5;
          v11 = (*(__int64 (__fastcall **)(SipFile *, __int64))(*(_QWORD *)v10 + 32LL))(v10, v12);
        }
        else
        {
          v11 = 87;
        }
      }
      else
      {
        v11 = 8;
      }
    }
    (**(void (__fastcall ***)(SipFile *, __int64))v10)(v10, 1);
    if ( v12 )
      (**(void (__fastcall ***)(__int64, __int64))v12)(v12, 1);
  }
  else
  {
    return 8;
  }
  return v11;
}

```

## disassembly

```asm
0x180004dd4  push    rbx
0x180004dd6  push    rbp
0x180004dd7  push    rsi
0x180004dd8  push    rdi
0x180004dd9  push    r14
0x180004ddb  sub     rsp, 20h
0x180004ddf  mov     ebp, r8d
0x180004de2  mov     rbx, rdx
0x180004de5  mov     r14, rcx
0x180004de8  test    r9, r9
0x180004deb  jz      short loc_180004DF4
0x180004ded  mov     dword ptr [r9], 0
0x180004df4  mov     rax, [rcx]
0x180004df7  mov     rax, [rax+8]
0x180004dfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e00  mov     rsi, rax
0x180004e03  test    rax, rax
0x180004e06  jnz     short loc_180004E10
0x180004e08  lea     ebx, [rax+8]
0x180004e0b  jmp     loc_180004EAA
0x180004e10  mov     r8b, 1; bool
0x180004e13  mov     rdx, rbx; struct SIP_SUBJECTINFO_ *
0x180004e16  mov     rcx, rsi; this
0x180004e19  xor     edi, edi
0x180004e1b  call    ?Open@SipFile@@QEAAKPEBUSIP_SUBJECTINFO_@@_N@Z; SipFile::Open(SIP_SUBJECTINFO_ const *,bool)
0x180004e20  mov     ebx, eax
0x180004e22  test    eax, eax
0x180004e24  jnz     short loc_180004E7F
0x180004e26  mov     rax, [r14]
0x180004e29  mov     rcx, r14
0x180004e2c  mov     rax, [rax+10h]
0x180004e30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e35  mov     rdi, rax
0x180004e38  test    rax, rax
0x180004e3b  jnz     short loc_180004E42
0x180004e3d  lea     ebx, [rax+8]
0x180004e40  jmp     short loc_180004E7F
0x180004e42  mov     eax, [rsi+38h]
0x180004e45  mov     rcx, [rsp+48h+arg_28]
0x180004e4a  mov     [rdi+8], ebp
0x180004e4d  mov     [rdi+1Ch], eax
0x180004e50  test    rcx, rcx
0x180004e53  jz      short loc_180004E7A
0x180004e55  mov     eax, [rsp+48h+arg_20]
0x180004e59  test    eax, eax
0x180004e5b  jz      short loc_180004E7A
0x180004e5d  mov     [rdi+10h], rcx
0x180004e61  mov     rdx, rdi
0x180004e64  mov     [rdi+0Ch], eax
0x180004e67  mov     rcx, rsi
0x180004e6a  mov     rax, [rsi]
0x180004e6d  mov     rax, [rax+20h]
0x180004e71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e76  mov     ebx, eax
0x180004e78  jmp     short loc_180004E7F
0x180004e7a  mov     ebx, 57h ; 'W'
0x180004e7f  mov     rax, [rsi]
0x180004e82  mov     edx, 1
0x180004e87  mov     rcx, rsi
0x180004e8a  mov     rax, [rax]
0x180004e8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e92  test    rdi, rdi
0x180004e95  jz      short loc_180004EAA
0x180004e97  mov     rax, [rdi]
0x180004e9a  mov     edx, 1
0x180004e9f  mov     rcx, rdi
0x180004ea2  mov     rax, [rax]
0x180004ea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004eaa  mov     eax, ebx
0x180004eac  add     rsp, 20h
0x180004eb0  pop     r14
0x180004eb2  pop     rdi
0x180004eb3  pop     rsi
0x180004eb4  pop     rbp
0x180004eb5  pop     rbx
0x180004eb6  retn
```
