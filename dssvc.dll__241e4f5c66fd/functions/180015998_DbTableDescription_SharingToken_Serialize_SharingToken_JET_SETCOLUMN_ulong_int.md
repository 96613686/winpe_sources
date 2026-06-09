# DbTableDescription<SharingToken>::Serialize(SharingToken *,JET_SETCOLUMN * *,ulong &,int &)

- ea: `0x180015998`
- end: `0x180015a5c`
- name: `?Serialize@?$DbTableDescription@VSharingToken@@@@SAJPEAVSharingToken@@PEAPEAUJET_SETCOLUMN@@AEAKAEAH@Z`
- size: `196`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800163ec`
- `0x180017ba8`

## callees

- `0x180003478`
- `0x18000be3c`
- `0x180015998`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall DbTableDescription<SharingToken>::Serialize(__int64 a1, char **a2, _DWORD *a3, __int64 a4)
{
  char *v8; // rbx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rax
  int v12; // edi

  if ( a1 && a2 )
  {
    v8 = (char *)operator new[](0x230u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v8 )
    {
      v9 = 0;
      *a3 = 14;
      v10 = 0;
      do
      {
        v11 = 7 * v9++;
        *(_DWORD *)&v8[v10] = qword_18002A380[v11];
        *(_QWORD *)&v8[v10 + 20] = 0;
        *(_QWORD *)&v8[v10 + 28] = 1;
        v10 += 40;
      }
      while ( v9 != 14 );
      v12 = (*(__int64 (__fastcall **)(__int64, char *, __int64, __int64))(*(_QWORD *)a1 + 16LL))(a1, v8, 14, a4);
      if ( v12 < 0 )
        Common::GlobalHeap::Free(v8);
      else
        *a2 = v8;
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180015998  push    rbx
0x18001599a  push    rbp
0x18001599b  push    rsi
0x18001599c  push    rdi
0x18001599d  push    r14
0x18001599f  sub     rsp, 30h
0x1800159a3  mov     rbp, r9
0x1800159a6  mov     r14, r8
0x1800159a9  mov     rsi, rdx
0x1800159ac  mov     rdi, rcx
0x1800159af  test    rcx, rcx
0x1800159b2  jz      loc_180015A4A
0x1800159b8  test    rdx, rdx
0x1800159bb  jz      loc_180015A4A
0x1800159c1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800159c8  mov     ecx, 230h; unsigned __int64
0x1800159cd  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800159d2  mov     rbx, rax
0x1800159d5  test    rax, rax
0x1800159d8  jz      short loc_180015A43
0x1800159da  xor     edx, edx
0x1800159dc  mov     dword ptr [r14], 0Eh
0x1800159e3  xor     ecx, ecx
0x1800159e5  imul    rax, rdx, 38h ; '8'
0x1800159e9  lea     r8, qword_18002A380
0x1800159f0  inc     rdx
0x1800159f3  mov     eax, [rax+r8]
0x1800159f7  mov     [rbx+rcx], eax
0x1800159fa  mov     qword ptr [rbx+rcx+14h], 0
0x180015a03  mov     qword ptr [rbx+rcx+1Ch], 1
0x180015a0c  lea     rcx, [rcx+28h]
0x180015a10  cmp     rdx, 0Eh
0x180015a14  jnz     short loc_1800159E5
0x180015a16  mov     rax, [rdi]
0x180015a19  mov     r8d, edx
0x180015a1c  mov     r9, rbp
0x180015a1f  mov     rdx, rbx
0x180015a22  mov     rcx, rdi
0x180015a25  mov     rax, [rax+10h]
0x180015a29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a2e  mov     edi, eax
0x180015a30  test    eax, eax
0x180015a32  js      short loc_180015A39
0x180015a34  mov     [rsi], rbx
0x180015a37  jmp     short loc_180015A4F
0x180015a39  mov     rcx, rbx; P
0x180015a3c  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180015a41  jmp     short loc_180015A4F
0x180015a43  mov     edi, 8007000Eh
0x180015a48  jmp     short loc_180015A4F
0x180015a4a  mov     edi, 80070057h
0x180015a4f  mov     eax, edi
0x180015a51  add     rsp, 30h
0x180015a55  pop     r14
0x180015a57  pop     rdi
0x180015a58  pop     rsi
0x180015a59  pop     rbp
0x180015a5a  pop     rbx
0x180015a5b  retn
```
