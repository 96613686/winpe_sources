# CMMCWatson::CreateSyncObjects(void)

- ea: `0x180012364`
- end: `0x180012432`
- name: `?CreateSyncObjects@CMMCWatson@@AEAA_NXZ`
- size: `206`
- prototype: `bool __fastcall(CMMCWatson *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012834`

## callees

- `0x180012364`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800123bc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800123d5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800123ef`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800123bc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800123d5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800123ef`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180012406`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180012406`

## pseudocode

```c
char __fastcall CMMCWatson::CreateSyncObjects(struct _SECURITY_ATTRIBUTES *this)
{
  char v1; // di
  struct _SECURITY_ATTRIBUTES *v3; // rsi
  HANDLE EventW; // rax
  HANDLE v5; // rax
  HANDLE v6; // rax
  HANDLE MutexW; // rax

  v1 = 0;
  if ( *(_QWORD *)&this[23].bInheritHandle )
  {
    if ( !*(_QWORD *)&this->nLength
      && !this->lpSecurityDescriptor
      && !*(_QWORD *)&this[1].nLength
      && !*(_QWORD *)&this->bInheritHandle )
    {
      v3 = this + 24;
      EventW = CreateEventW(this + 24, 0, 0, 0);
      *(_QWORD *)&this->nLength = EventW;
      if ( EventW )
      {
        v5 = CreateEventW(v3, 0, 0, 0);
        this->lpSecurityDescriptor = v5;
        if ( v5 )
        {
          v6 = CreateEventW(v3, 0, 0, 0);
          *(_QWORD *)&this[1].nLength = v6;
          if ( v6 )
          {
            MutexW = CreateMutexW(v3, 0, 0);
            *(_QWORD *)&this->bInheritHandle = MutexW;
            return MutexW != 0;
          }
        }
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180012364  mov     [rsp+arg_0], rbx
0x180012369  mov     [rsp+arg_8], rsi
0x18001236e  push    rdi
0x18001236f  sub     rsp, 20h
0x180012373  xor     dil, dil
0x180012376  mov     rbx, rcx
0x180012379  cmp     qword ptr [rcx+238h], 0
0x180012381  jz      loc_18001241F
0x180012387  cmp     qword ptr [rcx], 0
0x18001238b  jnz     loc_18001241F
0x180012391  cmp     qword ptr [rcx+8], 0
0x180012396  jnz     loc_18001241F
0x18001239c  cmp     qword ptr [rcx+18h], 0
0x1800123a1  jnz     short loc_18001241F
0x1800123a3  cmp     qword ptr [rcx+10h], 0
0x1800123a8  jnz     short loc_18001241F
0x1800123aa  lea     rsi, [rcx+240h]
0x1800123b1  xor     r9d, r9d; lpName
0x1800123b4  mov     rcx, rsi; lpEventAttributes
0x1800123b7  xor     r8d, r8d; bInitialState
0x1800123ba  xor     edx, edx; bManualReset
0x1800123bc  call    cs:__imp_CreateEventW
0x1800123c2  mov     [rbx], rax
0x1800123c5  test    rax, rax
0x1800123c8  jz      short loc_18001241F
0x1800123ca  xor     r9d, r9d; lpName
0x1800123cd  xor     r8d, r8d; bInitialState
0x1800123d0  xor     edx, edx; bManualReset
0x1800123d2  mov     rcx, rsi; lpEventAttributes
0x1800123d5  call    cs:__imp_CreateEventW
0x1800123db  mov     [rbx+8], rax
0x1800123df  test    rax, rax
0x1800123e2  jz      short loc_18001241F
0x1800123e4  xor     r9d, r9d; lpName
0x1800123e7  xor     r8d, r8d; bInitialState
0x1800123ea  xor     edx, edx; bManualReset
0x1800123ec  mov     rcx, rsi; lpEventAttributes
0x1800123ef  call    cs:__imp_CreateEventW
0x1800123f5  mov     [rbx+18h], rax
0x1800123f9  test    rax, rax
0x1800123fc  jz      short loc_18001241F
0x1800123fe  xor     r8d, r8d; lpName
0x180012401  xor     edx, edx; bInitialOwner
0x180012403  mov     rcx, rsi; lpMutexAttributes
0x180012406  call    cs:__imp_CreateMutexW
0x18001240c  movzx   edi, dil
0x180012410  mov     ecx, 1
0x180012415  test    rax, rax
0x180012418  mov     [rbx+10h], rax
0x18001241c  cmovnz  edi, ecx
0x18001241f  mov     rbx, [rsp+28h+arg_0]
0x180012424  mov     al, dil
0x180012427  mov     rsi, [rsp+28h+arg_8]
0x18001242c  add     rsp, 20h
0x180012430  pop     rdi
0x180012431  retn
```
