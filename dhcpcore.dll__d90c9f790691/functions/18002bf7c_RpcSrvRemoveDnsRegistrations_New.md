# RpcSrvRemoveDnsRegistrations_New

- ea: `0x18002bf7c`
- end: `0x18002c016`
- name: `RpcSrvRemoveDnsRegistrations_New`
- size: `154`
- prototype: `__int64 __fastcall(_WORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18002be80`

## callees

- `0x180001c48`
- `0x1800020d0`
- `0x1800021c0`
- `0x18002bf7c`
- `0x18004d1a0`
- `0x18004d1e0`

## import_xrefs

- `DNSAPI!DnsDhcpRemoveRegistrations` at `0x18002bfda`
- `DNSAPI!DnsDhcpRemoveRegistrations` at `0x18002bfda`

## pseudocode

```c
__int64 __fastcall RpcSrvRemoveDnsRegistrations_New(_WORD *a1)
{
  CRpcWatchDog *v2; // rcx
  unsigned int v3; // ebx
  int v4; // r8d
  CRpcWatchDog *v5; // rcx
  _OWORD v7[2]; // [rsp+20h] [rbp-28h] BYREF

  memset(v7, 0, sizeof(v7));
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_(1028, 78, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids);
  v3 = RpcValidateRequests(a1);
  if ( !v3 )
  {
    *(_QWORD *)&v7[0] = RpcSrvRemoveDnsRegistrations;
    CRpcWatchDog::AddEntry(v2, (struct _WatchDogEntry *)v7, v4);
    v3 = DnsDhcpRemoveRegistrations();
    CRpcWatchDog::RemoveEntry(v5, (struct _WatchDogEntry *)v7);
  }
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 79, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x18002bf7c  push    rbx
0x18002bf7e  sub     rsp, 40h
0x18002bf82  xorps   xmm0, xmm0
0x18002bf85  mov     rbx, rcx
0x18002bf88  movups  [rsp+48h+var_28], xmm0
0x18002bf8d  movups  [rsp+48h+var_18], xmm0
0x18002bf92  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002bf99  jz      short loc_18002BFB1
0x18002bf9b  mov     edx, 4Eh ; 'N'
0x18002bfa0  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002bfa7  mov     ecx, 404h
0x18002bfac  call    WPP_SF_
0x18002bfb1  mov     edx, 4
0x18002bfb6  mov     rcx, rbx
0x18002bfb9  call    RpcValidateRequests
0x18002bfbe  mov     ebx, eax
0x18002bfc0  test    eax, eax
0x18002bfc2  jnz     short loc_18002BFEC
0x18002bfc4  lea     rax, RpcSrvRemoveDnsRegistrations
0x18002bfcb  lea     rdx, [rsp+48h+var_28]; struct _WatchDogEntry *
0x18002bfd0  mov     qword ptr [rsp+48h+var_28], rax
0x18002bfd5  call    ?AddEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@H@Z; CRpcWatchDog::AddEntry(_WatchDogEntry *,int)
0x18002bfda  call    cs:__imp_DnsDhcpRemoveRegistrations
0x18002bfe0  mov     ebx, eax
0x18002bfe2  lea     rdx, [rsp+48h+var_28]; struct _WatchDogEntry *
0x18002bfe7  call    ?RemoveEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@@Z; CRpcWatchDog::RemoveEntry(_WatchDogEntry *)
0x18002bfec  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002bff3  jz      short loc_18002C00E
0x18002bff5  mov     edx, 4Fh ; 'O'
0x18002bffa  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002c001  mov     ecx, 404h
0x18002c006  mov     r9d, ebx
0x18002c009  call    WPP_SF_D
0x18002c00e  mov     eax, ebx
0x18002c010  add     rsp, 40h
0x18002c014  pop     rbx
0x18002c015  retn
```
