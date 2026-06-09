# FwInitPortCollCache(_tag_FW_PORT_COLLECTION_TYPE)

- ea: `0x18002094c`
- end: `0x180020a40`
- name: `?FwInitPortCollCache@@YAKW4_tag_FW_PORT_COLLECTION_TYPE@@@Z`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001dfb0`

## callees

- `0x180005e0c`
- `0x18002094c`
- `0x1800294b0`

## import_xrefs

- `fwbase!FwIOReadPortUseIndications` at `0x18002099c`
- `fwbase!FwIOReadPortUseIndications` at `0x18002099c`
- `fwbase!FwBaseFree` at `0x180020a0e`
- `fwbase!FwBaseFree` at `0x180020a0e`
- `fwbase!FwHResultToWindowsError` at `0x180020a1c`
- `fwbase!FwHResultToWindowsError` at `0x180020a1c`

## pseudocode

```c
__int64 __fastcall FwInitPortCollCache(__int64 a1)
{
  int v1; // ebx
  __int64 v2; // rsi
  struct _tag_FW_PORT_COLLECTION_CACHE near **v3; // rdi
  __int64 i; // r9
  __int64 v6; // [rsp+20h] [rbp-38h] BYREF

  v1 = 0;
  v6 = 0;
  if ( !dword_18009C2F0 )
  {
    v2 = 2LL * (int)a1;
    dword_18009C2F0 = 1;
    v3 = &PortCollCache + 2 * (int)a1;
    v1 = FwIOReadPortUseIndications(a1, &v6, v3 + 1);
    if ( v1 >= 0 )
    {
      for ( i = 0; (unsigned int)i < *((_DWORD *)v3 + 2); i = (unsigned int)(i + 1) )
        *((_DWORD *)*(&PortCollCache + v2) + i) = *(_DWORD *)(v6 + 4 * i);
    }
    else if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        WPP_a5b3657941d83b93491a297b9144c2a3_Traceguids,
        (unsigned int)v1);
    }
    if ( v6 )
      FwBaseFree(v6);
  }
  return FwHResultToWindowsError((unsigned int)v1);
}

```

## disassembly

```asm
0x18002094c  push    rbx
0x18002094e  push    rsi
0x18002094f  push    rdi
0x180020950  push    r14
0x180020952  sub     rsp, 38h
0x180020956  mov     rax, cs:__security_cookie
0x18002095d  xor     rax, rsp
0x180020960  mov     [rsp+58h+var_30], rax
0x180020965  xor     ebx, ebx
0x180020967  cmp     cs:dword_18009C2F0, ebx
0x18002096d  mov     [rsp+58h+var_38], rbx
0x180020972  jnz     loc_180020A1A
0x180020978  movsxd  rsi, ecx
0x18002097b  lea     r14, ?PortCollCache@@3PAU_tag_FW_PORT_COLLECTION_CACHE@@A; _tag_FW_PORT_COLLECTION_CACHE near * PortCollCache
0x180020982  add     rsi, rsi
0x180020985  mov     cs:dword_18009C2F0, 1
0x18002098f  lea     rdx, [rsp+58h+var_38]
0x180020994  lea     rdi, [r14+rsi*8]
0x180020998  lea     r8, [rdi+8]
0x18002099c  call    cs:__imp_FwIOReadPortUseIndications
0x1800209a3  nop     dword ptr [rax+rax+00h]
0x1800209a8  mov     ebx, eax
0x1800209aa  test    eax, eax
0x1800209ac  jns     short loc_1800209E1
0x1800209ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800209b5  lea     rax, WPP_GLOBAL_Control
0x1800209bc  cmp     rcx, rax
0x1800209bf  jz      short loc_180020A04
0x1800209c1  test    byte ptr [rcx+1Ch], 1
0x1800209c5  jz      short loc_180020A04
0x1800209c7  mov     rcx, [rcx+10h]
0x1800209cb  lea     r8, WPP_a5b3657941d83b93491a297b9144c2a3_Traceguids
0x1800209d2  mov     edx, 1Dh
0x1800209d7  mov     r9d, ebx
0x1800209da  call    WPP_SF_d
0x1800209df  jmp     short loc_180020A04
0x1800209e1  xor     r9d, r9d
0x1800209e4  cmp     [rdi+8], r9d
0x1800209e8  jbe     short loc_180020A04
0x1800209ea  mov     rax, [rsp+58h+var_38]
0x1800209ef  mov     rdx, [r14+rsi*8]
0x1800209f3  mov     ecx, [rax+r9*4]
0x1800209f7  mov     [rdx+r9*4], ecx
0x1800209fb  inc     r9d
0x1800209fe  cmp     r9d, [rdi+8]
0x180020a02  jb      short loc_1800209EA
0x180020a04  mov     rcx, [rsp+58h+var_38]
0x180020a09  test    rcx, rcx
0x180020a0c  jz      short loc_180020A1A
0x180020a0e  call    cs:__imp_FwBaseFree
0x180020a15  nop     dword ptr [rax+rax+00h]
0x180020a1a  mov     ecx, ebx
0x180020a1c  call    cs:__imp_FwHResultToWindowsError
0x180020a23  nop     dword ptr [rax+rax+00h]
0x180020a28  mov     rcx, [rsp+58h+var_30]
0x180020a2d  xor     rcx, rsp; StackCookie
0x180020a30  call    __security_check_cookie
0x180020a35  add     rsp, 38h
0x180020a39  pop     r14
0x180020a3b  pop     rdi
0x180020a3c  pop     rsi
0x180020a3d  pop     rbx
0x180020a3e  retn
```
