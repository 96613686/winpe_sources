# RemoveWork::WorkCallback(void)

- ea: `0x18000c1c0`
- end: `0x18000c25d`
- name: `?WorkCallback@RemoveWork@@UEAAXXZ`
- size: `157`
- prototype: `void __fastcall(CWiGigDAFProviderAssociation **this)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000a810`
- `0x18000c1c0`
- `0x18000c308`
- `0x18001f010`

## pseudocode

```c
void __fastcall RemoveWork::WorkCallback(CWiGigDAFProviderAssociation **this)
{
  CWiGigDAFProviderAssociation *v2; // rdi
  void (__fastcall *v3)(CWiGigDAFProviderAssociation *, _QWORD); // rbx
  unsigned int v4; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this);
  }
  v2 = this[1];
  v3 = *(void (__fastcall **)(CWiGigDAFProviderAssociation *, _QWORD))(*(_QWORD *)v2 + 72LL);
  v4 = CWiGigDAFProviderAssociation::RemoveAssociation(this[2]);
  v3(v2, v4);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this);
  }
}

```

## disassembly

```asm
0x18000c1c0  push    rbx
0x18000c1c2  push    rbp
0x18000c1c3  push    rsi
0x18000c1c4  push    rdi
0x18000c1c5  sub     rsp, 28h
0x18000c1c9  mov     rsi, rcx
0x18000c1cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c1d3  lea     rbp, WPP_GLOBAL_Control
0x18000c1da  cmp     rcx, rbp
0x18000c1dd  jz      short loc_18000C203
0x18000c1df  cmp     byte ptr [rcx+19h], 4
0x18000c1e3  jb      short loc_18000C203
0x18000c1e5  test    byte ptr [rcx+1Ch], 1
0x18000c1e9  jz      short loc_18000C203
0x18000c1eb  mov     rcx, [rcx+10h]
0x18000c1ef  lea     r8, WPP_c2da2149000737c368804296c411cd66_Traceguids
0x18000c1f6  mov     edx, 16h
0x18000c1fb  mov     r9, rsi
0x18000c1fe  call    WPP_SF_q
0x18000c203  mov     rdi, [rsi+8]
0x18000c207  mov     rcx, [rsi+10h]; this
0x18000c20b  mov     rax, [rdi]
0x18000c20e  mov     rbx, [rax+48h]
0x18000c212  call    ?RemoveAssociation@CWiGigDAFProviderAssociation@@QEAAJXZ; CWiGigDAFProviderAssociation::RemoveAssociation(void)
0x18000c217  mov     edx, eax
0x18000c219  mov     rcx, rdi
0x18000c21c  mov     rax, rbx
0x18000c21f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c224  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c22b  cmp     rcx, rbp
0x18000c22e  jz      short loc_18000C254
0x18000c230  cmp     byte ptr [rcx+19h], 4
0x18000c234  jb      short loc_18000C254
0x18000c236  test    byte ptr [rcx+1Ch], 1
0x18000c23a  jz      short loc_18000C254
0x18000c23c  mov     rcx, [rcx+10h]
0x18000c240  lea     r8, WPP_c2da2149000737c368804296c411cd66_Traceguids
0x18000c247  mov     edx, 17h
0x18000c24c  mov     r9, rsi
0x18000c24f  call    WPP_SF_q
0x18000c254  add     rsp, 28h
0x18000c258  pop     rdi
0x18000c259  pop     rsi
0x18000c25a  pop     rbp
0x18000c25b  pop     rbx
0x18000c25c  retn
```
