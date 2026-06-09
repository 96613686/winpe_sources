# RxOrphanSrvOpens

- ea: `0x1400441c0`
- end: `0x140044277`
- name: `RxOrphanSrvOpens`
- size: `183`
- prototype: `void __stdcall(PV_NET_ROOT ThisVNetRoot)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x140010e40`
- `0x140050910`

## callees

- `0x1400120c0`
- `0x1400441c0`
- `0x14006a520`
- `0x140074600`
- `0x140074810`
- `0x140074a00`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400441f7`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400441f7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004425a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14007ba24`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004425a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14007ba24`

## pseudocode

```c
void __stdcall RxOrphanSrvOpens(PV_NET_ROOT ThisVNetRoot)
{
  struct _MRX_NET_ROOT_ *v1; // rdx
  char v2; // r8
  UNICODE_STRING *v3; // rdi
  char *i; // rax
  _OWORD v6[3]; // [rsp+20h] [rbp-38h] BYREF

  v3 = (UNICODE_STRING *)v1;
  if ( *((_BYTE *)&ThisVNetRoot->1 + 77) != 5 )
  {
    if ( v2 )
      RxDrainIOForSrvOpens((__int64)ThisVNetRoot, v1);
    ExAcquireResourceExclusiveLite((PERESOURCE)((char *)&ThisVNetRoot[1].1 + 56), 1u);
    memset(v6, 0, sizeof(v6));
    for ( i = (char *)RxFcbTableLookupFirstFcb(&ThisVNetRoot[1].NetRoot, 0, 0, v6);
          i;
          i = (char *)RxFcbTableLookupNextFcb(v6) )
    {
      RxOrphanSrvOpensForFcb(i, v3);
    }
    RxFcbTableEndLookup(v6);
    ExReleaseResourceLite((PERESOURCE)((char *)&ThisVNetRoot[1].1 + 56));
  }
}

```

## disassembly

```asm
0x1400441c0  mov     [rsp+arg_8], rbx
0x1400441c5  mov     [rsp+arg_10], rsi
0x1400441ca  mov     [rsp+arg_0], rcx
0x1400441cf  push    rdi
0x1400441d0  sub     rsp, 50h
0x1400441d4  mov     rdi, rdx
0x1400441d7  mov     rbx, rcx
0x1400441da  cmp     byte ptr [rcx+4Dh], 5
0x1400441de  jz      loc_140044266
0x1400441e4  test    r8b, r8b
0x1400441e7  jz      short loc_1400441EE
0x1400441e9  call    RxDrainIOForSrvOpens
0x1400441ee  lea     rcx, [rbx+158h]; Resource
0x1400441f5  mov     dl, 1; Wait
0x1400441f7  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400441fe  nop     dword ptr [rax+rax+00h]
0x140044203  nop
0x140044204  xorps   xmm0, xmm0
0x140044207  movups  [rsp+58h+var_38], xmm0
0x14004420c  movups  [rsp+58h+var_28], xmm0
0x140044211  movups  [rsp+58h+var_18], xmm0
0x140044216  lea     r9, [rsp+58h+var_38]
0x14004421b  xor     r8d, r8d
0x14004421e  xor     edx, edx
0x140044220  lea     rcx, [rbx+128h]
0x140044227  call    RxFcbTableLookupFirstFcb
0x14004422c  test    rax, rax
0x14004422f  jz      short loc_140044248
0x140044231  mov     rdx, rdi
0x140044234  mov     rcx, rax; Instance
0x140044237  call    RxOrphanSrvOpensForFcb
0x14004423c  lea     rcx, [rsp+58h+var_38]
0x140044241  call    RxFcbTableLookupNextFcb
0x140044246  jmp     short loc_14004422C
0x140044248  lea     rcx, [rsp+58h+var_38]
0x14004424d  call    RxFcbTableEndLookup
0x140044252  nop
0x140044253  lea     rcx, [rbx+158h]; Resource
0x14004425a  call    cs:__imp_ExReleaseResourceLite
0x140044261  nop     dword ptr [rax+rax+00h]
0x140044266  mov     rbx, [rsp+58h+arg_8]
0x14004426b  mov     rsi, [rsp+58h+arg_10]
0x140044270  add     rsp, 50h
0x140044274  pop     rdi
0x140044275  retn
0x14007ba10  push    rbp
0x14007ba12  sub     rsp, 20h
0x14007ba16  mov     rbp, rdx
0x14007ba19  mov     rcx, [rbp+60h]
0x14007ba1d  add     rcx, 158h; Resource
0x14007ba24  call    cs:__imp_ExReleaseResourceLite
0x14007ba2b  nop     dword ptr [rax+rax+00h]
0x14007ba30  nop
0x14007ba31  add     rsp, 20h
0x14007ba35  pop     rbp
0x14007ba36  retn
```
