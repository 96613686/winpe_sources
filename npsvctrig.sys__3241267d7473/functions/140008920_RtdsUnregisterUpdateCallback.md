# RtdsUnregisterUpdateCallback

- ea: `0x140008920`
- end: `0x1400089d5`
- name: `RtdsUnregisterUpdateCallback`
- size: `181`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140008250`
- `0x1400088cc`
- `0x14000b080`

## callees

- `0x140001760`
- `0x140001780`
- `0x140008920`

## import_xrefs

- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x1400089af`
- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x1400089af`

## pseudocode

```c
__int64 __fastcall RtdsUnregisterUpdateCallback(_QWORD *a1)
{
  unsigned int v1; // ebx
  unsigned int i; // edx
  __int64 *v4; // r9
  __int64 v5; // rcx
  __int64 v6; // rdi
  struct _KMUTANT *v7; // rcx

  v1 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= 2 )
      return (unsigned int)-1073741275;
    v4 = (__int64 *)(&off_140004000)[2 * i];
    v5 = *a1 - *v4;
    if ( *a1 == *v4 )
      v5 = a1[1] - v4[1];
    if ( !v5 )
      break;
  }
  v6 = 7LL * i;
  RtdspLock((&off_1400050D0)[v6]);
  v7 = (struct _KMUTANT *)(&off_1400050D0)[v6];
  if ( qword_1400050B8[v6] )
  {
    qword_1400050B8[v6] = 0;
    RtdspUnlock(v7);
    ExUnsubscribeWnfStateChange(qword_1400050C0[v6]);
  }
  else
  {
    v1 = -1073741811;
    RtdspUnlock(v7);
  }
  return v1;
}

```

## disassembly

```asm
0x140008920  mov     [rsp+arg_0], rbx
0x140008925  mov     [rsp+arg_8], rsi
0x14000892a  push    rdi
0x14000892b  sub     rsp, 20h
0x14000892f  xor     ebx, ebx
0x140008931  lea     rsi, cs:140000000h
0x140008938  mov     edx, ebx
0x14000893a  mov     r8, rcx
0x14000893d  cmp     edx, 2
0x140008940  jnb     short loc_1400089BD
0x140008942  mov     rcx, [r8]
0x140008945  mov     eax, edx
0x140008947  add     rax, rax
0x14000894a  mov     r10d, edx
0x14000894d  mov     r9, ds:rva off_140004000[rsi+rax*8]
0x140008955  sub     rcx, [r9]
0x140008958  jnz     short loc_140008962
0x14000895a  mov     rcx, [r8+8]
0x14000895e  sub     rcx, [r9+8]
0x140008962  test    rcx, rcx
0x140008965  jz      short loc_14000896B
0x140008967  inc     edx
0x140008969  jmp     short loc_14000893D
0x14000896b  imul    rdi, r10, 38h ; '8'
0x14000896f  mov     rcx, [rdi+rsi+50D0h]
0x140008977  call    RtdspLock
0x14000897c  mov     rcx, [rdi+rsi+50D0h]
0x140008984  cmp     [rdi+rsi+50B8h], rbx
0x14000898c  jnz     short loc_14000899A
0x14000898e  mov     ebx, 0C000000Dh
0x140008993  call    RtdspUnlock
0x140008998  jmp     short loc_1400089C2
0x14000899a  mov     [rdi+rsi+50B8h], rbx
0x1400089a2  call    RtdspUnlock
0x1400089a7  mov     rcx, [rdi+rsi+50C0h]
0x1400089af  call    cs:__imp_ExUnsubscribeWnfStateChange
0x1400089b6  nop     dword ptr [rax+rax+00h]
0x1400089bb  jmp     short loc_1400089C2
0x1400089bd  mov     ebx, 0C0000225h
0x1400089c2  mov     rsi, [rsp+28h+arg_8]
0x1400089c7  mov     eax, ebx
0x1400089c9  mov     rbx, [rsp+28h+arg_0]
0x1400089ce  add     rsp, 20h
0x1400089d2  pop     rdi
0x1400089d3  retn
```
