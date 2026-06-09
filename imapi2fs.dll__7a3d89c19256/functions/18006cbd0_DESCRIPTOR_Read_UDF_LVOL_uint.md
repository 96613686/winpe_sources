# DESCRIPTOR::Read(UDF_LVOL *,uint *)

- ea: `0x18006cbd0`
- end: `0x18006cd97`
- name: `?Read@DESCRIPTOR@@QEAAEPEAVUDF_LVOL@@PEAI@Z`
- size: `455`
- prototype: `unsigned __int8(DESCRIPTOR *__hidden this, struct UDF_LVOL *, unsigned int *)`
- caller_count: `17`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18001f4b4`
- `0x180062f38`
- `0x180063a90`
- `0x180065438`
- `0x18006800c`
- `0x180068858`
- `0x180068a9c`
- `0x18006e10c`
- `0x18006fad0`
- `0x1800706ac`
- `0x180070d28`
- `0x180070fd4`
- `0x180071944`
- `0x1800722b4`
- `0x1800723d0`
- `0x1800728b8`
- `0x180073994`

## callees

- `0x1800063b8`
- `0x18005e5e4`
- `0x18005fae0`
- `0x180067f4c`
- `0x18006cbd0`
- `0x180088010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18006cc12`
- `ntdll!RtlAllocateHeap` at `0x18006cc12`

## pseudocode

```c
unsigned __int8 __fastcall DESCRIPTOR::Read(DESCRIPTOR *this, struct UDF_LVOL *a2, unsigned int *a3)
{
  UDF_SA *v4; // rcx
  unsigned int SectorSize; // eax
  PVOID Heap; // rax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rdx
  unsigned int v14; // eax
  unsigned int v15; // esi
  __int64 v16; // rbp
  unsigned int v17; // eax
  __int64 v18; // rax
  unsigned int v19; // eax
  unsigned int v20; // [rsp+50h] [rbp+8h] BYREF

  *((_BYTE *)this + 26) = 1;
  v4 = (UDF_SA *)*((_QWORD *)a2 + 4);
  v20 = 0;
  SectorSize = UDF_SA::QuerySectorSize(v4);
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, SectorSize);
  *((_QWORD *)this + 2) = Heap;
  if ( !Heap )
    return 0;
  if ( !UDF_LVOL::Read(a2, *((_WORD *)this + 12), *((_DWORD *)this + 7), 1u, Heap) )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return 0;
    v10 = 13;
    goto LABEL_10;
  }
  v11 = *((_QWORD *)this + 2);
  v12 = *((_QWORD *)a2 + 4);
  *a3 = 1;
  if ( *(_WORD *)(v12 + 78) != *(_WORD *)(v11 + 6) )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return 0;
    v10 = 14;
    goto LABEL_10;
  }
  if ( !(*(unsigned __int8 (__fastcall **)(DESCRIPTOR *, unsigned int *))(*(_QWORD *)this + 24LL))(this, &v20) )
    return 0;
  v14 = UDF_SA::QuerySectorSize(*((UDF_SA **)a2 + 4));
  v15 = (v14 + (unsigned __int64)v20 - 1) / v14;
  if ( v15 != 1 )
  {
    v16 = *((_QWORD *)this + 2);
    v17 = UDF_SA::QuerySectorSize(*((UDF_SA **)a2 + 4));
    v18 = UlibRealloc(*((PVOID *)this + 2), v15 * v17);
    *((_QWORD *)this + 2) = v18;
    if ( !v18 )
    {
      *((_QWORD *)this + 2) = v16;
      return 0;
    }
    v19 = UDF_SA::QuerySectorSize(*((UDF_SA **)a2 + 4));
    if ( !UDF_LVOL::Read(
            a2,
            *((_WORD *)this + 12),
            *((_DWORD *)this + 7) + 1,
            v15 - 1,
            (void *)(*((_QWORD *)this + 2) + v19)) )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return 0;
      v10 = 15;
LABEL_10:
      WPP_SF_d(v9[2], v10, WPP_53c0d9234996324c1c730ec4a7bb0b63_Traceguids);
      return 0;
    }
    *a3 = v15;
  }
  return 1;
}

```

## disassembly

```asm
0x18006cbd0  mov     [rsp+arg_8], rbx
0x18006cbd5  mov     [rsp+arg_10], rbp
0x18006cbda  push    rsi
0x18006cbdb  push    rdi
0x18006cbdc  push    r14
0x18006cbde  sub     rsp, 30h
0x18006cbe2  mov     rbx, rcx
0x18006cbe5  mov     byte ptr [rcx+1Ah], 1
0x18006cbe9  mov     rcx, [rdx+20h]; this
0x18006cbed  mov     r14, r8
0x18006cbf0  mov     rdi, rdx
0x18006cbf3  mov     [rsp+48h+arg_0], 0
0x18006cbfb  call    ?QuerySectorSize@UDF_SA@@QEBAKXZ; UDF_SA::QuerySectorSize(void)
0x18006cc00  mov     rcx, gs:60h
0x18006cc09  xor     edx, edx; Flags
0x18006cc0b  mov     r8d, eax; Size
0x18006cc0e  mov     rcx, [rcx+30h]; HeapHandle
0x18006cc12  call    cs:__imp_RtlAllocateHeap
0x18006cc18  mov     [rbx+10h], rax
0x18006cc1c  test    rax, rax
0x18006cc1f  jz      loc_18006CCAF
0x18006cc25  mov     r8d, [rbx+1Ch]; unsigned int
0x18006cc29  mov     r9d, 1; unsigned int
0x18006cc2f  movzx   edx, word ptr [rbx+18h]; unsigned __int16
0x18006cc33  mov     rcx, rdi; this
0x18006cc36  mov     [rsp+48h+var_28], rax; void *
0x18006cc3b  call    ?Read@UDF_LVOL@@QEAAEGKKPEAX@Z; UDF_LVOL::Read(ushort,ulong,ulong,void *)
0x18006cc40  test    al, al
0x18006cc42  jnz     short loc_18006CC64
0x18006cc44  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cc4b  lea     rax, WPP_GLOBAL_Control
0x18006cc52  cmp     rcx, rax
0x18006cc55  jz      short loc_18006CCAF
0x18006cc57  test    byte ptr [rcx+1Ch], 1
0x18006cc5b  jz      short loc_18006CCAF
0x18006cc5d  mov     edx, 0Dh
0x18006cc62  jmp     short loc_18006CC9B
0x18006cc64  mov     rax, [rbx+10h]
0x18006cc68  mov     rdx, [rdi+20h]
0x18006cc6c  mov     dword ptr [r14], 1
0x18006cc73  movzx   ecx, word ptr [rax+6]
0x18006cc77  cmp     [rdx+4Eh], cx
0x18006cc7b  jz      short loc_18006CCC4
0x18006cc7d  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cc84  lea     rax, WPP_GLOBAL_Control
0x18006cc8b  cmp     rcx, rax
0x18006cc8e  jz      short loc_18006CCAF
0x18006cc90  test    byte ptr [rcx+1Ch], 1
0x18006cc94  jz      short loc_18006CCAF
0x18006cc96  mov     edx, 0Eh
0x18006cc9b  mov     r9d, [rbx+1Ch]
0x18006cc9f  mov     rcx, [rcx+10h]
0x18006cca3  lea     r8, WPP_53c0d9234996324c1c730ec4a7bb0b63_Traceguids
0x18006ccaa  call    WPP_SF_d
0x18006ccaf  xor     al, al
0x18006ccb1  mov     rbx, [rsp+48h+arg_8]
0x18006ccb6  mov     rbp, [rsp+48h+arg_10]
0x18006ccbb  add     rsp, 30h
0x18006ccbf  pop     r14
0x18006ccc1  pop     rdi
0x18006ccc2  pop     rsi
0x18006ccc3  retn
0x18006ccc4  mov     rax, [rbx]
0x18006ccc7  lea     rdx, [rsp+48h+arg_0]
0x18006cccc  mov     rcx, rbx
0x18006cccf  mov     rax, [rax+18h]
0x18006ccd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ccd8  test    al, al
0x18006ccda  jz      short loc_18006CCAF
0x18006ccdc  mov     rcx, [rdi+20h]; this
0x18006cce0  call    ?QuerySectorSize@UDF_SA@@QEBAKXZ; UDF_SA::QuerySectorSize(void)
0x18006cce5  mov     ecx, eax
0x18006cce7  xor     edx, edx
0x18006cce9  mov     eax, [rsp+48h+arg_0]
0x18006cced  dec     rax
0x18006ccf0  add     rax, rcx
0x18006ccf3  div     rcx
0x18006ccf6  mov     rsi, rax
0x18006ccf9  cmp     eax, 1
0x18006ccfc  jz      loc_18006CD90
0x18006cd02  mov     rcx, [rdi+20h]; this
0x18006cd06  mov     rbp, [rbx+10h]
0x18006cd0a  call    ?QuerySectorSize@UDF_SA@@QEBAKXZ; UDF_SA::QuerySectorSize(void)
0x18006cd0f  mov     rcx, [rbx+10h]; P
0x18006cd13  imul    eax, esi
0x18006cd16  mov     edx, eax; Size
0x18006cd18  call    UlibRealloc
0x18006cd1d  mov     [rbx+10h], rax
0x18006cd21  test    rax, rax
0x18006cd24  jnz     short loc_18006CD2C
0x18006cd26  mov     [rbx+10h], rbp
0x18006cd2a  jmp     short loc_18006CCAF
0x18006cd2c  mov     rcx, [rdi+20h]; this
0x18006cd30  call    ?QuerySectorSize@UDF_SA@@QEBAKXZ; UDF_SA::QuerySectorSize(void)
0x18006cd35  mov     r8d, [rbx+1Ch]
0x18006cd39  lea     r9d, [rsi-1]; unsigned int
0x18006cd3d  movzx   edx, word ptr [rbx+18h]; unsigned __int16
0x18006cd41  inc     r8d; unsigned int
0x18006cd44  mov     ecx, eax
0x18006cd46  add     rcx, [rbx+10h]
0x18006cd4a  mov     [rsp+48h+var_28], rcx; void *
0x18006cd4f  mov     rcx, rdi; this
0x18006cd52  call    ?Read@UDF_LVOL@@QEAAEGKKPEAX@Z; UDF_LVOL::Read(ushort,ulong,ulong,void *)
0x18006cd57  test    al, al
0x18006cd59  jnz     short loc_18006CD8D
0x18006cd5b  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cd62  lea     rax, WPP_GLOBAL_Control
0x18006cd69  cmp     rcx, rax
0x18006cd6c  jz      loc_18006CCAF
0x18006cd72  test    byte ptr [rcx+1Ch], 1
0x18006cd76  jz      loc_18006CCAF
0x18006cd7c  mov     r9d, [rbx+1Ch]
0x18006cd80  mov     edx, 0Fh
0x18006cd85  inc     r9d
0x18006cd88  jmp     loc_18006CC9F
0x18006cd8d  mov     [r14], esi
0x18006cd90  mov     al, 1
0x18006cd92  jmp     loc_18006CCB1
```
