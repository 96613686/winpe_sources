# DhcpSetThreadCompartmentScopeAll

- ea: `0x180011388`
- end: `0x18001144c`
- name: `DhcpSetThreadCompartmentScopeAll`
- size: `196`
- prototype: `__int64 __fastcall(__int64, int *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180023928`

## callees

- `0x180011388`
- `0x18004c5f8`
- `0x18004d1e0`

## import_xrefs

- `IPHLPAPI!GetCurrentThreadCompartmentScope` at `0x1800113fc`
- `IPHLPAPI!GetCurrentThreadCompartmentScope` at `0x1800113fc`
- `IPHLPAPI!SetCurrentThreadCompartmentScope` at `0x18001140b`
- `IPHLPAPI!SetCurrentThreadCompartmentScope` at `0x18001140b`

## pseudocode

```c
__int64 __fastcall DhcpSetThreadCompartmentScopeAll(__int64 a1, int *a2, __int64 a3)
{
  _DWORD *v4; // rsi
  int v5; // ebp
  unsigned int v6; // ebx
  UINT32 CompartmentScope; // [rsp+50h] [rbp+8h] BYREF
  UINT32 CompartmentId; // [rsp+58h] [rbp+10h] BYREF

  CompartmentId = 0;
  v4 = (_DWORD *)a1;
  CompartmentScope = 0;
  v5 = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_(1028, 18, WPP_7a9c28c0d9d83b6f632816efa12309d5_Traceguids);
  if ( v4 )
    *v4 = 0;
  if ( a2 )
    *a2 = 0;
  if ( !v4 || !a2 )
  {
    v6 = 87;
    goto LABEL_15;
  }
  v6 = 0;
  if ( DhcpGlobalCompartmentAware )
  {
    GetCurrentThreadCompartmentScope(&CompartmentScope, &CompartmentId);
    a1 = 0xFFFFFFFFLL;
    if ( CompartmentScope != -1 )
    {
      v6 = SetCurrentThreadCompartmentScope(0xFFFFFFFF);
      if ( v6 )
        goto LABEL_15;
      v5 = 1;
    }
    *v4 = CompartmentScope;
    *a2 = v5;
  }
LABEL_15:
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_dlD(a1, a2, a3, CompartmentScope, v5, v6);
  return v6;
}

```

## disassembly

```asm
0x180011388  mov     [rsp+arg_10], rbx
0x18001138d  push    rbp
0x18001138e  push    rsi
0x18001138f  push    rdi
0x180011390  sub     rsp, 30h
0x180011394  mov     rdi, rdx
0x180011397  mov     [rsp+48h+CompartmentId], 0
0x18001139f  mov     rsi, rcx
0x1800113a2  mov     [rsp+48h+CompartmentScope], 0
0x1800113aa  xor     ebp, ebp
0x1800113ac  test    byte ptr cs:xmmword_1800616A0, 10h
0x1800113b3  jz      short loc_1800113C9
0x1800113b5  lea     edx, [rbp+12h]
0x1800113b8  mov     ecx, 404h
0x1800113bd  lea     r8, WPP_7a9c28c0d9d83b6f632816efa12309d5_Traceguids
0x1800113c4  call    WPP_SF_
0x1800113c9  test    rsi, rsi
0x1800113cc  jz      short loc_1800113D0
0x1800113ce  mov     [rsi], ebp
0x1800113d0  test    rdi, rdi
0x1800113d3  jz      short loc_1800113D7
0x1800113d5  mov     [rdi], ebp
0x1800113d7  test    rsi, rsi
0x1800113da  jnz     short loc_1800113E3
0x1800113dc  mov     ebx, 57h ; 'W'
0x1800113e1  jmp     short loc_180011422
0x1800113e3  test    rdi, rdi
0x1800113e6  jz      short loc_1800113DC
0x1800113e8  xor     ebx, ebx
0x1800113ea  cmp     cs:DhcpGlobalCompartmentAware, ebx
0x1800113f0  jz      short loc_180011422
0x1800113f2  lea     rdx, [rsp+48h+CompartmentId]; CompartmentId
0x1800113f7  lea     rcx, [rsp+48h+CompartmentScope]; CompartmentScope
0x1800113fc  call    cs:__imp_GetCurrentThreadCompartmentScope
0x180011402  or      ecx, 0FFFFFFFFh; CompartmentScope
0x180011405  cmp     [rsp+48h+CompartmentScope], ecx
0x180011409  jz      short loc_18001141A
0x18001140b  call    cs:__imp_SetCurrentThreadCompartmentScope
0x180011411  mov     ebx, eax
0x180011413  test    eax, eax
0x180011415  jnz     short loc_180011422
0x180011417  lea     ebp, [rax+1]
0x18001141a  mov     eax, [rsp+48h+CompartmentScope]
0x18001141e  mov     [rsi], eax
0x180011420  mov     [rdi], ebp
0x180011422  test    byte ptr cs:xmmword_1800616A0, 10h
0x180011429  jz      short loc_18001143D
0x18001142b  mov     r9d, [rsp+48h+CompartmentScope]
0x180011430  mov     [rsp+48h+var_20], ebx
0x180011434  mov     [rsp+48h+var_28], ebp
0x180011438  call    WPP_SF_dlD
0x18001143d  mov     eax, ebx
0x18001143f  mov     rbx, [rsp+48h+arg_10]
0x180011444  add     rsp, 30h
0x180011448  pop     rdi
0x180011449  pop     rsi
0x18001144a  pop     rbp
0x18001144b  retn
```
