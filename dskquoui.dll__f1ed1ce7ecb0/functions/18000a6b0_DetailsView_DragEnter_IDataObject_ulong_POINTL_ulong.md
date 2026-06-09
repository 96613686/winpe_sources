# DetailsView::DragEnter(IDataObject *,ulong,_POINTL,ulong *)

- ea: `0x18000a6b0`
- end: `0x18000a7af`
- name: `?DragEnter@DetailsView@@UEAAJPEAUIDataObject@@KU_POINTL@@PEAK@Z`
- size: `255`
- prototype: `__int64 __fastcall(DetailsView *__hidden this, struct IDataObject *, unsigned int, struct _POINTL, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18000a6b0`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall DetailsView::DragEnter(
        DetailsView *this,
        struct IDataObject *a2,
        char a3,
        struct _POINTL a4,
        unsigned int *a5)
{
  unsigned int *v5; // r14
  int v9; // edi
  int v10; // ebp
  __int128 v12; // [rsp+30h] [rbp-58h] BYREF
  __int128 v13; // [rsp+40h] [rbp-48h]
  __int64 v14; // [rsp+98h] [rbp+10h] BYREF

  v5 = a5;
  v14 = 0;
  *a5 = 0;
  v9 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))a2->lpVtbl->EnumFormatEtc)(a2, 1, &v14, a4);
  if ( v9 >= 0 )
  {
    LODWORD(a5) = 0;
    v12 = 0;
    v13 = 0;
    while ( 1 )
    {
      v10 = 0;
      if ( (*(unsigned int (__fastcall **)(__int64, __int64, __int128 *, unsigned int **))(*(_QWORD *)v14 + 24LL))(
             v14,
             1,
             &v12,
             &a5) )
      {
        break;
      }
      if ( ((_WORD)v12 == DetailsView::DataObject::m_CF_NtDiskQuotaExport || (_WORD)v12 == 15) && (BYTE8(v13) & 5) != 0 )
      {
        v10 = 1;
        break;
      }
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v9 = 0;
    if ( v10 )
    {
      *v5 = 2 - ((a3 & 8) != 0);
      *((_QWORD *)this + 27) = a2;
      ((void (__fastcall *)(struct IDataObject *))a2->lpVtbl->AddRef)(a2);
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000a6b0  mov     r11, rsp
0x18000a6b3  push    rbx
0x18000a6b4  push    rbp
0x18000a6b5  push    rsi
0x18000a6b6  push    rdi
0x18000a6b7  push    r14
0x18000a6b9  push    r15
0x18000a6bb  sub     rsp, 58h
0x18000a6bf  mov     r14, [rsp+88h+arg_20]
0x18000a6c7  mov     rsi, rdx
0x18000a6ca  mov     ebx, r8d
0x18000a6cd  mov     qword ptr [r11+10h], 0
0x18000a6d5  mov     r15, rcx
0x18000a6d8  lea     r8, [r11+10h]
0x18000a6dc  mov     rcx, rsi
0x18000a6df  mov     dword ptr [r14], 0
0x18000a6e6  mov     rax, [rdx]
0x18000a6e9  mov     edx, 1
0x18000a6ee  mov     rax, [rax+40h]
0x18000a6f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6f7  mov     edi, eax
0x18000a6f9  test    eax, eax
0x18000a6fb  js      loc_18000A7A0
0x18000a701  xorps   xmm0, xmm0
0x18000a704  mov     dword ptr [rsp+88h+arg_20], 0
0x18000a70f  movups  [rsp+88h+var_58], xmm0
0x18000a714  movups  [rsp+88h+var_48], xmm0
0x18000a719  mov     rcx, [rsp+88h+arg_8]
0x18000a721  lea     r9, [rsp+88h+arg_20]
0x18000a729  xor     ebp, ebp
0x18000a72b  lea     r8, [rsp+88h+var_58]
0x18000a730  mov     rax, [rcx]
0x18000a733  lea     edx, [rbp+1]
0x18000a736  mov     rax, [rax+18h]
0x18000a73a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a73f  test    eax, eax
0x18000a741  jnz     short loc_18000A763
0x18000a743  movzx   eax, word ptr [rsp+88h+var_58]
0x18000a748  cmp     ax, cs:?m_CF_NtDiskQuotaExport@DataObject@DetailsView@@2GA; ushort DetailsView::DataObject::m_CF_NtDiskQuotaExport
0x18000a74f  jz      short loc_18000A757
0x18000a751  cmp     ax, 0Fh
0x18000a755  jnz     short loc_18000A719
0x18000a757  test    byte ptr [rsp+88h+var_48+8], 5
0x18000a75c  jz      short loc_18000A719
0x18000a75e  mov     ebp, 1
0x18000a763  mov     rcx, [rsp+88h+arg_8]
0x18000a76b  mov     rax, [rcx]
0x18000a76e  mov     rax, [rax+10h]
0x18000a772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a777  xor     edi, edi
0x18000a779  test    ebp, ebp
0x18000a77b  jz      short loc_18000A7A0
0x18000a77d  and     bl, 8
0x18000a780  mov     rcx, rsi
0x18000a783  neg     bl
0x18000a785  sbb     eax, eax
0x18000a787  add     eax, 2
0x18000a78a  mov     [r14], eax
0x18000a78d  mov     [r15+0D8h], rsi
0x18000a794  mov     rax, [rsi]
0x18000a797  mov     rax, [rax+8]
0x18000a79b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7a0  mov     eax, edi
0x18000a7a2  add     rsp, 58h
0x18000a7a6  pop     r15
0x18000a7a8  pop     r14
0x18000a7aa  pop     rdi
0x18000a7ab  pop     rsi
0x18000a7ac  pop     rbp
0x18000a7ad  pop     rbx
0x18000a7ae  retn
```
