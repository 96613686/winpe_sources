# DbTableDescription<SharingToken>::GetSCBasedOnPK(SharingToken *,_jetSeekCriteria * *,ulong &)

- ea: `0x18001577c`
- end: `0x18001580b`
- name: `?GetSCBasedOnPK@?$DbTableDescription@VSharingToken@@@@SAJPEAVSharingToken@@PEAPEAU_jetSeekCriteria@@AEAK@Z`
- size: `143`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _DWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001669c`
- `0x180017ba8`

## callees

- `0x180003478`
- `0x18000be3c`
- `0x18001577c`

## pseudocode

```c
__int64 __fastcall DbTableDescription<SharingToken>::GetSCBasedOnPK(__int64 a1, _QWORD *a2, _DWORD *a3)
{
  __int64 result; // rax
  _OWORD *v7; // rax
  void *v8; // rbx
  _DWORD *v9; // rcx

  if ( !a2 || !a1 )
    return 2147942487LL;
  v7 = operator new[](0x10u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v7;
  if ( v7 )
  {
    *v7 = *(_OWORD *)(a1 + 12);
    v9 = operator new[](0x10u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v9 )
    {
      result = 0;
      *(_QWORD *)v9 = v8;
      v9[2] = 16;
      v9[3] = 1;
      *a2 = v9;
      *a3 = 1;
      return result;
    }
    Common::GlobalHeap::Free(v8);
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x18001577c  push    rbx
0x18001577e  push    rsi
0x18001577f  push    rdi
0x180015780  push    r14
0x180015782  sub     rsp, 28h
0x180015786  mov     r14, r8
0x180015789  mov     rsi, rdx
0x18001578c  mov     rdi, rcx
0x18001578f  test    rdx, rdx
0x180015792  jnz     short loc_18001579B
0x180015794  mov     eax, 80070057h
0x180015799  jmp     short loc_180015801
0x18001579b  test    rdi, rdi
0x18001579e  jz      short loc_180015794
0x1800157a0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800157a7  mov     ecx, 10h; unsigned __int64
0x1800157ac  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800157b1  mov     rbx, rax
0x1800157b4  test    rax, rax
0x1800157b7  jz      short loc_1800157FC
0x1800157b9  movups  xmm0, xmmword ptr [rdi+0Ch]
0x1800157bd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800157c4  mov     ecx, 10h; unsigned __int64
0x1800157c9  movdqu  xmmword ptr [rax], xmm0
0x1800157cd  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800157d2  mov     rcx, rax
0x1800157d5  test    rax, rax
0x1800157d8  jz      short loc_1800157F4
0x1800157da  xor     eax, eax
0x1800157dc  mov     [rcx], rbx
0x1800157df  mov     dword ptr [rcx+8], 10h
0x1800157e6  lea     edx, [rax+1]
0x1800157e9  mov     [rcx+0Ch], edx
0x1800157ec  mov     [rsi], rcx
0x1800157ef  mov     [r14], edx
0x1800157f2  jmp     short loc_180015801
0x1800157f4  mov     rcx, rbx; P
0x1800157f7  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x1800157fc  mov     eax, 8007000Eh
0x180015801  add     rsp, 28h
0x180015805  pop     r14
0x180015807  pop     rdi
0x180015808  pop     rsi
0x180015809  pop     rbx
0x18001580a  retn
```
