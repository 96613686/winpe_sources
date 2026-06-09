# RpcSrvMadcapGenUID

- ea: `0x18002a450`
- end: `0x18002a533`
- name: `RpcSrvMadcapGenUID`
- size: `227`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x1800020d0`
- `0x1800021c0`
- `0x18002a450`
- `0x180037c9c`
- `0x18004d1a0`
- `0x18004d1e0`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18002a4ad`
- `RPCRT4!RpcImpersonateClient` at `0x18002a4ad`
- `RPCRT4!RpcRevertToSelf` at `0x18002a516`
- `RPCRT4!RpcRevertToSelf` at `0x18002a516`

## pseudocode

```c
__int64 __fastcall RpcSrvMadcapGenUID(CRpcWatchDog *a1, __int64 a2, int a3)
{
  unsigned int v4; // ebx
  unsigned int v5; // eax
  _OWORD v7[2]; // [rsp+20h] [rbp-28h] BYREF

  memset(v7, 0, sizeof(v7));
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_(1028, 241, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids);
  if ( !a2 )
  {
    v4 = 87;
    goto LABEL_8;
  }
  *(_QWORD *)&v7[0] = RpcSrvMadcapGenUID;
  CRpcWatchDog::AddEntry(a1, (struct _WatchDogEntry *)v7, a3);
  v5 = RpcImpersonateClient(0);
  v4 = v5;
  if ( !v5 )
  {
    v4 = GenMadcapClientUID(*(_QWORD *)a2, (unsigned int *)(a2 + 8));
    RpcRevertToSelf();
LABEL_13:
    CRpcWatchDog::RemoveEntry(a1, (struct _WatchDogEntry *)v7);
    return v4;
  }
  LODWORD(a2) = 1;
  if ( (xmmword_1800616A0 & 2) != 0 )
  {
    WPP_SF_D(1025, 242, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v5);
LABEL_8:
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_D(1025, 243, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v4);
  }
  if ( (_DWORD)a2 )
    goto LABEL_13;
  return v4;
}

```

## disassembly

```asm
0x18002a450  mov     [rsp+arg_0], rbx
0x18002a455  push    rdi
0x18002a456  sub     rsp, 40h
0x18002a45a  xorps   xmm0, xmm0
0x18002a45d  mov     rdi, rdx
0x18002a460  movups  [rsp+48h+var_28], xmm0
0x18002a465  movups  [rsp+48h+var_18], xmm0
0x18002a46a  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002a471  jz      short loc_18002A489
0x18002a473  mov     edx, 0F1h
0x18002a478  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002a47f  mov     ecx, 404h
0x18002a484  call    WPP_SF_
0x18002a489  test    rdi, rdi
0x18002a48c  jnz     short loc_18002A495
0x18002a48e  mov     ebx, 57h ; 'W'
0x18002a493  jmp     short loc_18002A4E0
0x18002a495  lea     rax, RpcSrvMadcapGenUID
0x18002a49c  lea     rdx, [rsp+48h+var_28]; struct _WatchDogEntry *
0x18002a4a1  mov     qword ptr [rsp+48h+var_28], rax
0x18002a4a6  call    ?AddEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@H@Z; CRpcWatchDog::AddEntry(_WatchDogEntry *,int)
0x18002a4ab  xor     ecx, ecx; BindingHandle
0x18002a4ad  call    cs:__imp_RpcImpersonateClient
0x18002a4b3  mov     ebx, eax
0x18002a4b5  test    eax, eax
0x18002a4b7  jz      short loc_18002A508
0x18002a4b9  mov     edi, 1
0x18002a4be  test    byte ptr cs:xmmword_1800616A0, 2
0x18002a4c5  jz      short loc_18002A502
0x18002a4c7  mov     edx, 0F2h
0x18002a4cc  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002a4d3  mov     ecx, 401h
0x18002a4d8  mov     r9d, eax
0x18002a4db  call    WPP_SF_D
0x18002a4e0  test    byte ptr cs:xmmword_1800616A0, 2
0x18002a4e7  jz      short loc_18002A502
0x18002a4e9  mov     edx, 0F3h
0x18002a4ee  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002a4f5  mov     ecx, 401h
0x18002a4fa  mov     r9d, ebx
0x18002a4fd  call    WPP_SF_D
0x18002a502  test    edi, edi
0x18002a504  jz      short loc_18002A526
0x18002a506  jmp     short loc_18002A51C
0x18002a508  mov     rcx, [rdi]
0x18002a50b  lea     rdx, [rdi+8]
0x18002a50f  call    GenMadcapClientUID
0x18002a514  mov     ebx, eax
0x18002a516  call    cs:__imp_RpcRevertToSelf
0x18002a51c  lea     rdx, [rsp+48h+var_28]; struct _WatchDogEntry *
0x18002a521  call    ?RemoveEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@@Z; CRpcWatchDog::RemoveEntry(_WatchDogEntry *)
0x18002a526  mov     eax, ebx
0x18002a528  mov     rbx, [rsp+48h+arg_0]
0x18002a52d  add     rsp, 40h
0x18002a531  pop     rdi
0x18002a532  retn
```
