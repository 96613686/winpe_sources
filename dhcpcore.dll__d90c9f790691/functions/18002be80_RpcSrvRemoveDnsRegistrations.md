# RpcSrvRemoveDnsRegistrations

- ea: `0x18002be80`
- end: `0x18002bf74`
- name: `RpcSrvRemoveDnsRegistrations`
- size: `244`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x180001c48`
- `0x1800020d0`
- `0x1800021c0`
- `0x18002be80`
- `0x18002bf7c`
- `0x18004d1a0`
- `0x18004d1e0`

## import_xrefs

- `DNSAPI!DnsDhcpRemoveRegistrations` at `0x18002bf38`
- `DNSAPI!DnsDhcpRemoveRegistrations` at `0x18002bf38`

## pseudocode

```c
__int64 __fastcall RpcSrvRemoveDnsRegistrations(_WORD *a1)
{
  unsigned int v3; // eax
  CRpcWatchDog *v4; // rcx
  int v5; // r8d
  unsigned int v6; // ebx
  unsigned int v7; // eax
  CRpcWatchDog *v8; // rcx
  _OWORD v9[2]; // [rsp+20h] [rbp-28h] BYREF

  memset(v9, 0, sizeof(v9));
  if ( g_fVelocityApistubStyleUpdate )
    return RpcSrvRemoveDnsRegistrations_New(a1);
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_(1028, 80, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids);
  v3 = RpcValidateRequests(a1);
  v6 = v3;
  if ( v3 )
  {
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_D(1025, 83, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v3);
  }
  else
  {
    *(_QWORD *)&v9[0] = RpcSrvRemoveDnsRegistrations;
    CRpcWatchDog::AddEntry(v4, (struct _WatchDogEntry *)v9, v5);
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_(1028, 81, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids);
    v7 = DnsDhcpRemoveRegistrations();
    v6 = v7;
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_D(1028, 82, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v7);
    CRpcWatchDog::RemoveEntry(v8, (struct _WatchDogEntry *)v9);
  }
  return v6;
}

```

## disassembly

```asm
0x18002be80  push    rbx
0x18002be82  sub     rsp, 40h
0x18002be86  cmp     cs:g_fVelocityApistubStyleUpdate, 0
0x18002be8d  xorps   xmm0, xmm0
0x18002be90  movups  [rsp+48h+var_28], xmm0
0x18002be95  mov     rbx, rcx
0x18002be98  movups  [rsp+48h+var_18], xmm0
0x18002be9d  jz      short loc_18002BEA9
0x18002be9f  call    RpcSrvRemoveDnsRegistrations_New
0x18002bea4  jmp     loc_18002BF6E
0x18002bea9  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002beb0  jz      short loc_18002BEC8
0x18002beb2  mov     edx, 50h ; 'P'
0x18002beb7  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002bebe  mov     ecx, 404h
0x18002bec3  call    WPP_SF_
0x18002bec8  mov     edx, 4
0x18002becd  mov     rcx, rbx
0x18002bed0  call    RpcValidateRequests
0x18002bed5  mov     ebx, eax
0x18002bed7  test    eax, eax
0x18002bed9  jz      short loc_18002BF03
0x18002bedb  test    byte ptr cs:xmmword_1800616A0, 2
0x18002bee2  jz      loc_18002BF6C
0x18002bee8  mov     edx, 53h ; 'S'
0x18002beed  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002bef4  mov     ecx, 401h
0x18002bef9  mov     r9d, eax
0x18002befc  call    WPP_SF_D
0x18002bf01  jmp     short loc_18002BF6C
0x18002bf03  lea     rax, RpcSrvRemoveDnsRegistrations
0x18002bf0a  lea     rdx, [rsp+48h+var_28]; struct _WatchDogEntry *
0x18002bf0f  mov     qword ptr [rsp+48h+var_28], rax
0x18002bf14  call    ?AddEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@H@Z; CRpcWatchDog::AddEntry(_WatchDogEntry *,int)
0x18002bf19  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002bf20  jz      short loc_18002BF38
0x18002bf22  mov     edx, 51h ; 'Q'
0x18002bf27  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002bf2e  mov     ecx, 404h
0x18002bf33  call    WPP_SF_
0x18002bf38  call    cs:__imp_DnsDhcpRemoveRegistrations
0x18002bf3e  mov     ebx, eax
0x18002bf40  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002bf47  jz      short loc_18002BF62
0x18002bf49  mov     edx, 52h ; 'R'
0x18002bf4e  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002bf55  mov     ecx, 404h
0x18002bf5a  mov     r9d, eax
0x18002bf5d  call    WPP_SF_D
0x18002bf62  lea     rdx, [rsp+48h+var_28]; struct _WatchDogEntry *
0x18002bf67  call    ?RemoveEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@@Z; CRpcWatchDog::RemoveEntry(_WatchDogEntry *)
0x18002bf6c  mov     eax, ebx
0x18002bf6e  add     rsp, 40h
0x18002bf72  pop     rbx
0x18002bf73  retn
```
