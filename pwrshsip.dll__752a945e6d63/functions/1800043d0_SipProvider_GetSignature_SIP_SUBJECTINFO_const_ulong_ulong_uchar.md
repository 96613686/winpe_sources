# SipProvider::GetSignature(SIP_SUBJECTINFO_ const *,ulong *,ulong *,uchar *)

- ea: `0x1800043d0`
- end: `0x1800044e3`
- name: `?GetSignature@SipProvider@@QEAAKPEBUSIP_SUBJECTINFO_@@PEAK1PEAE@Z`
- size: `275`
- prototype: `unsigned int(SipProvider *__hidden this, const struct SIP_SUBJECTINFO_ *, unsigned int *, unsigned int *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004b00`

## callees

- `0x1800043d0`
- `0x180004834`
- `0x1800054a2`
- `0x180006010`

## pseudocode

```c
__int64 __fastcall SipProvider::GetSignature(
        SipProvider *this,
        const struct SIP_SUBJECTINFO_ *a2,
        unsigned int *a3,
        unsigned int *a4,
        unsigned __int8 *a5)
{
  void (__fastcall ***v9)(_QWORD, __int64); // rcx
  SipFile *v10; // rax
  SipFile *v11; // rsi
  unsigned int v12; // ebx
  __int64 v13; // r8
  unsigned int v14; // eax
  __int64 v15; // rdx
  unsigned __int8 *v16; // rcx
  __int64 v18; // [rsp+58h] [rbp+10h] BYREF

  v9 = 0;
  v18 = 0;
  if ( a2 && a3 && a4 )
  {
    *a3 = 0;
    v10 = (SipFile *)(*(__int64 (__fastcall **)(SipProvider *))(*(_QWORD *)this + 8LL))(this);
    v11 = v10;
    if ( v10 )
    {
      v12 = SipFile::Open(v10, a2, 0);
      if ( !v12 )
      {
        v14 = (*(__int64 (__fastcall **)(SipFile *, __int64 *))(*(_QWORD *)v11 + 40LL))(v11, &v18);
        v12 = v14;
        if ( v14 == 1168 )
        {
          *a4 = 0;
          v12 = 0;
        }
        else if ( !v14 )
        {
          v15 = v18;
          v16 = a5;
          *a3 = *(_DWORD *)(v18 + 8);
          v13 = *a4;
          *a4 = *(_DWORD *)(v15 + 12);
          if ( v16 )
          {
            if ( *(_DWORD *)(v15 + 12) <= (unsigned int)v13 )
              memcpy_0(v16, *(const void **)(v15 + 16), *(unsigned int *)(v15 + 12));
            else
              v12 = 122;
          }
        }
      }
      (**(void (__fastcall ***)(SipFile *, __int64, __int64))v11)(v11, 1, v13);
    }
    else
    {
      v12 = 8;
    }
    v9 = (void (__fastcall ***)(_QWORD, __int64))v18;
  }
  else
  {
    v12 = 87;
  }
  if ( v9 )
    (**v9)(v9, 1);
  return v12;
}

```

## disassembly

```asm
0x1800043d0  push    rbx
0x1800043d2  push    rsi
0x1800043d3  push    rdi
0x1800043d4  push    r14
0x1800043d6  sub     rsp, 28h
0x1800043da  mov     rbx, rdx
0x1800043dd  mov     rdi, r9
0x1800043e0  mov     rdx, rcx
0x1800043e3  mov     r14, r8
0x1800043e6  xor     ecx, ecx
0x1800043e8  mov     [rsp+48h+arg_8], rcx
0x1800043ed  test    rbx, rbx
0x1800043f0  jz      loc_1800044BD
0x1800043f6  test    r8, r8
0x1800043f9  jz      loc_1800044BD
0x1800043ff  test    r9, r9
0x180004402  jz      loc_1800044BD
0x180004408  mov     [r8], ecx
0x18000440b  mov     rcx, rdx
0x18000440e  mov     rax, [rdx]
0x180004411  mov     rax, [rax+8]
0x180004415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000441a  mov     rsi, rax
0x18000441d  test    rax, rax
0x180004420  jnz     short loc_18000442F
0x180004422  lea     ebx, [rax+8]
0x180004425  mov     rcx, [rsp+48h+arg_8]
0x18000442a  jmp     loc_1800044C2
0x18000442f  xor     r8d, r8d; bool
0x180004432  mov     rdx, rbx; struct SIP_SUBJECTINFO_ *
0x180004435  mov     rcx, rsi; this
0x180004438  call    ?Open@SipFile@@QEAAKPEBUSIP_SUBJECTINFO_@@_N@Z; SipFile::Open(SIP_SUBJECTINFO_ const *,bool)
0x18000443d  mov     ebx, eax
0x18000443f  test    eax, eax
0x180004441  jnz     short loc_1800044A5
0x180004443  mov     rax, [rsi]
0x180004446  lea     rdx, [rsp+48h+arg_8]
0x18000444b  mov     rcx, rsi
0x18000444e  mov     rax, [rax+28h]
0x180004452  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004457  mov     ebx, eax
0x180004459  cmp     eax, 490h
0x18000445e  jnz     short loc_18000446A
0x180004460  mov     dword ptr [rdi], 0
0x180004466  xor     ebx, ebx
0x180004468  jmp     short loc_1800044A5
0x18000446a  test    eax, eax
0x18000446c  jnz     short loc_1800044A5
0x18000446e  mov     rdx, [rsp+48h+arg_8]
0x180004473  mov     rcx, [rsp+48h+arg_20]; void *
0x180004478  mov     eax, [rdx+8]
0x18000447b  mov     [r14], eax
0x18000447e  mov     r8d, [rdi]
0x180004481  mov     eax, [rdx+0Ch]
0x180004484  mov     [rdi], eax
0x180004486  test    rcx, rcx
0x180004489  jz      short loc_1800044A5
0x18000448b  cmp     [rdx+0Ch], r8d
0x18000448f  jbe     short loc_180004498
0x180004491  mov     ebx, 7Ah ; 'z'
0x180004496  jmp     short loc_1800044A5
0x180004498  mov     r8d, [rdx+0Ch]; Size
0x18000449c  mov     rdx, [rdx+10h]; Src
0x1800044a0  call    memcpy_0
0x1800044a5  mov     rax, [rsi]
0x1800044a8  mov     edx, 1
0x1800044ad  mov     rcx, rsi
0x1800044b0  mov     rax, [rax]
0x1800044b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044b8  jmp     loc_180004425
0x1800044bd  mov     ebx, 57h ; 'W'
0x1800044c2  test    rcx, rcx
0x1800044c5  jz      short loc_1800044D7
0x1800044c7  mov     rax, [rcx]
0x1800044ca  mov     edx, 1
0x1800044cf  mov     rax, [rax]
0x1800044d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044d7  mov     eax, ebx
0x1800044d9  add     rsp, 28h
0x1800044dd  pop     r14
0x1800044df  pop     rdi
0x1800044e0  pop     rsi
0x1800044e1  pop     rbx
0x1800044e2  retn
```
