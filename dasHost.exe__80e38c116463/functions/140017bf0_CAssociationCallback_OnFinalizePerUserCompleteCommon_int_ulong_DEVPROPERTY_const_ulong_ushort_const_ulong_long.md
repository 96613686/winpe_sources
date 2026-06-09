# CAssociationCallback::OnFinalizePerUserCompleteCommon(int,ulong,_DEVPROPERTY * const,ulong,ushort const * *,ulong,long)

- ea: `0x140017bf0`
- end: `0x140017d42`
- name: `?OnFinalizePerUserCompleteCommon@CAssociationCallback@@IEAAJHKQEAU_DEVPROPERTY@@KPEAPEBGKJ@Z`
- size: `338`
- prototype: `__int64 __fastcall(CAssociationCallback *this, int, unsigned int, struct _DEVPROPERTY *const, unsigned int, unsigned __int16 **, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140017b80`
- `0x140017bb0`
- `0x140017d50`

## callees

- `0x14000b5d4`
- `0x140017bf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140017d2b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140017d2b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140017cdf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140017cdf`

## pseudocode

```c
__int64 __fastcall CAssociationCallback::OnFinalizePerUserCompleteCommon(
        CAssociationCallback *this,
        int a2,
        unsigned int a3,
        struct _DEVPROPERTY *const a4,
        unsigned int a5,
        unsigned __int16 **a6,
        unsigned int a7,
        unsigned int a8)
{
  unsigned int v12; // ebx
  unsigned int v13; // ecx
  int v14; // r8d
  unsigned int v15; // edx
  unsigned int v16; // ebx

  if ( a3 )
  {
    if ( !a4 )
      goto LABEL_26;
  }
  else if ( a4 )
  {
    goto LABEL_26;
  }
  if ( !a5 )
  {
    if ( !a6 )
      goto LABEL_9;
LABEL_26:
    v12 = -2147024809;
    goto LABEL_27;
  }
  if ( !a6 )
    goto LABEL_26;
LABEL_9:
  v12 = a8;
  v13 = 0;
  if ( !a8 )
  {
    while ( v13 < a5 )
    {
      if ( !a6[v13] )
        goto LABEL_26;
      ++v13;
    }
    if ( *((_DWORD *)this + 14) && (a3 || a4) )
      goto LABEL_26;
  }
  v14 = 0;
  v15 = 0;
  if ( !a8 )
  {
    while ( v15 < a3 )
    {
      if ( a4[v15].CompKey.Key.pid == 2
        && DEVPKEY_Aep_ContainerId == *(_QWORD *)&a4[v15].CompKey.Key.fmtid.Data1
        && *(_QWORD *)a4[v15].CompKey.Key.fmtid.Data4 == 0xC5D430B359BE8B8CuLL
        && a4[v15].CompKey.Store == DEVPROP_STORE_SYSTEM )
      {
        v14 = 1;
        break;
      }
      ++v15;
    }
    if ( !*((_DWORD *)this + 14) && !v14 )
      goto LABEL_26;
  }
LABEL_27:
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  if ( *((_DWORD *)this + 26) )
    v16 = OnFinalizeCompleteStub(a2, a3, a4, a5, (const unsigned __int16 **)a6, a7, v12, *((RTL_SRWLOCK **)this + 4));
  else
    v16 = -2140930029;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  return v16;
}

```

## disassembly

```asm
0x140017bf0  push    rbx
0x140017bf2  push    rbp
0x140017bf3  push    rsi
0x140017bf4  push    rdi
0x140017bf5  push    r13
0x140017bf7  push    r14
0x140017bf9  push    r15
0x140017bfb  sub     rsp, 40h
0x140017bff  mov     r14, [rsp+78h+arg_28]
0x140017c07  xor     r11d, r11d
0x140017c0a  mov     rsi, r9
0x140017c0d  mov     r15d, r8d
0x140017c10  mov     r13d, edx
0x140017c13  mov     rbp, rcx
0x140017c16  test    r8d, r8d
0x140017c19  jz      short loc_140017C26
0x140017c1b  test    r9, r9
0x140017c1e  jz      loc_140017CD6
0x140017c24  jmp     short loc_140017C2F
0x140017c26  test    rsi, rsi
0x140017c29  jnz     loc_140017CD6
0x140017c2f  cmp     [rsp+78h+arg_20], r11d
0x140017c37  jz      short loc_140017C44
0x140017c39  test    r14, r14
0x140017c3c  jz      loc_140017CD6
0x140017c42  jmp     short loc_140017C4D
0x140017c44  test    r14, r14
0x140017c47  jnz     loc_140017CD6
0x140017c4d  mov     ebx, [rsp+78h+arg_38]
0x140017c54  mov     ecx, r11d
0x140017c57  test    ebx, ebx
0x140017c59  jnz     short loc_140017C80
0x140017c5b  cmp     ecx, [rsp+78h+arg_20]
0x140017c62  jnb     short loc_140017C70
0x140017c64  mov     eax, ecx
0x140017c66  cmp     [r14+rax*8], r11
0x140017c6a  jz      short loc_140017CD6
0x140017c6c  inc     ecx
0x140017c6e  jmp     short loc_140017C5B
0x140017c70  cmp     [rbp+38h], r11d
0x140017c74  jz      short loc_140017C80
0x140017c76  test    r15d, r15d
0x140017c79  jnz     short loc_140017CD6
0x140017c7b  test    rsi, rsi
0x140017c7e  jnz     short loc_140017CD6
0x140017c80  mov     r8d, r11d
0x140017c83  mov     edx, r11d
0x140017c86  test    ebx, ebx
0x140017c88  jnz     short loc_140017CDB
0x140017c8a  mov     r9, cs:qword_1400215D0
0x140017c91  mov     r10, cs:DEVPKEY_Aep_ContainerId
0x140017c98  cmp     edx, r15d
0x140017c9b  jnb     short loc_140017CCB
0x140017c9d  mov     eax, edx
0x140017c9f  lea     rcx, [rax+rax*2]
0x140017ca3  add     rcx, rcx
0x140017ca6  cmp     dword ptr [rsi+rcx*8+10h], 2
0x140017cab  jnz     short loc_140017CC1
0x140017cad  cmp     r10, [rsi+rcx*8]
0x140017cb1  jnz     short loc_140017CC1
0x140017cb3  cmp     r9, [rsi+rcx*8+8]
0x140017cb8  jnz     short loc_140017CC1
0x140017cba  cmp     [rsi+rcx*8+14h], r11d
0x140017cbf  jz      short loc_140017CC5
0x140017cc1  inc     edx
0x140017cc3  jmp     short loc_140017C98
0x140017cc5  mov     r8d, 1
0x140017ccb  cmp     [rbp+38h], r11d
0x140017ccf  jnz     short loc_140017CDB
0x140017cd1  test    r8d, r8d
0x140017cd4  jnz     short loc_140017CDB
0x140017cd6  mov     ebx, 80070057h
0x140017cdb  lea     rcx, [rbp+70h]; lpCriticalSection
0x140017cdf  call    cs:__imp_EnterCriticalSection
0x140017ce5  cmp     dword ptr [rbp+68h], 0
0x140017ce9  jz      short loc_140017D22
0x140017ceb  mov     rax, [rbp+20h]
0x140017cef  mov     r8, rsi; struct _DEVPROPERTY *
0x140017cf2  mov     r9d, [rsp+78h+arg_20]; unsigned int
0x140017cfa  mov     edx, r15d; unsigned int
0x140017cfd  mov     [rsp+78h+var_40], rax; void *
0x140017d02  mov     ecx, r13d; int
0x140017d05  mov     eax, [rsp+78h+arg_30]
0x140017d0c  mov     [rsp+78h+var_48], ebx; int
0x140017d10  mov     [rsp+78h+var_50], eax; unsigned int
0x140017d14  mov     [rsp+78h+var_58], r14; unsigned __int16 **
0x140017d19  call    ?OnFinalizeCompleteStub@@YAJHKQEAU_DEVPROPERTY@@KPEAPEBGKJPEAX@Z; OnFinalizeCompleteStub(int,ulong,_DEVPROPERTY * const,ulong,ushort const * *,ulong,long,void *)
0x140017d1e  mov     ebx, eax
0x140017d20  jmp     short loc_140017D27
0x140017d22  mov     ebx, 80640013h
0x140017d27  lea     rcx, [rbp+70h]; lpCriticalSection
0x140017d2b  call    cs:__imp_LeaveCriticalSection
0x140017d31  mov     eax, ebx
0x140017d33  add     rsp, 40h
0x140017d37  pop     r15
0x140017d39  pop     r14
0x140017d3b  pop     r13
0x140017d3d  pop     rdi
0x140017d3e  pop     rsi
0x140017d3f  pop     rbp
0x140017d40  pop     rbx
0x140017d41  retn
```
