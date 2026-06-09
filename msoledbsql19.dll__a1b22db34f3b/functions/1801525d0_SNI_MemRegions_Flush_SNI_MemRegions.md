# SNI_MemRegions::Flush(SNI_MemRegions *)

- ea: `0x1801525d0`
- end: `0x180152768`
- name: `?Flush@SNI_MemRegions@@SAXPEAV1@@Z`
- size: `408`
- prototype: `void __fastcall(struct SNI_MemRegions *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180156f90`
- `0x1801596a0`

## callees

- `0x1800030c0`
- `0x180003824`
- `0x1801525d0`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18015271c`
- `KERNEL32!GetLastError` at `0x18015271c`
- `KERNEL32!InterlockedPopEntrySList` at `0x18015261d`
- `KERNEL32!InterlockedPopEntrySList` at `0x18015261d`
- `KERNEL32!CloseHandle` at `0x180152712`
- `KERNEL32!CloseHandle` at `0x180152712`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SNI_MemRegions::Flush(struct SNI_MemRegions *a1)
{
  __int64 *v1; // r14
  __int64 v2; // r15
  __int64 v3; // rbp
  unsigned int i; // edi
  PSLIST_ENTRY v5; // rax
  PSLIST_ENTRY v6; // rbx
  __int64 Next_high; // rax
  __int64 v8; // rsi
  __int64 v9; // rcx
  __int64 v10; // r8
  void (__fastcall *v11)(_QWORD, _QWORD, __int64, struct _SLIST_ENTRY *); // rax
  void *v12; // rcx
  DWORD LastError; // eax

  v1 = (__int64 *)((char *)a1 + 8);
  v2 = 16;
  do
  {
    if ( *v1 )
    {
      v3 = *v1;
      for ( i = 0; i < 8; ++i )
      {
        while ( 1 )
        {
          v5 = InterlockedPopEntrySList((PSLIST_HEADER)(v3 + 48LL * i));
          v6 = v5;
          if ( !v5 )
            break;
          Next_high = SHIDWORD(v5[9].Next);
          if ( (_DWORD)Next_high && bidID != -1 )
            ((void (__fastcall *)(__int64, char *, __int64, __int64, _QWORD))off_180248098)(
              bidID,
              `SNI_Packet::~SNI_Packet'::`4'::_bidPtrSA_053_261[0],
              5,
              Next_high,
              0);
          HIDWORD(v6[9].Next) = 0;
          v8 = *((_QWORD *)&v6[4].Next + 1);
          if ( v8 && (unsigned int)(*((_DWORD *)&v6[8].Next + 3) - 3) > 1 )
          {
            v9 = *((_QWORD *)&v6->Next + 1);
            v10 = *((unsigned int *)qword_1801ECE38 + LOBYTE(v6[8].Next));
            v11 = *(void (__fastcall **)(_QWORD, _QWORD, __int64, struct _SLIST_ENTRY *))(v9 + 40);
            if ( v11 )
              v11(*(_QWORD *)(v9 + 24), *((_QWORD *)&v6[4].Next + 1), v10, v6[10].Next);
            (*(void (__fastcall **)(struct ISOSHost_MemObj *, __int64, __int64))(*(_QWORD *)g_pMO + 128LL))(
              g_pMO,
              v8,
              v10);
          }
          *((_QWORD *)&v6[4].Next + 1) = 0;
          v6[10].Next = 0;
          v12 = (void *)*((_QWORD *)&v6[7].Next + 1);
          if ( v12 )
          {
            if ( !CloseHandle(v12) )
            {
              LastError = GetLastError();
              if ( (bidGblFlags & 2) != 0 )
              {
                if ( `SNI_Packet::~SNI_Packet'::`21'::_bidPtrSA_030_288[0] )
                  bidTraceW(
                    `SNI_Packet::~SNI_Packet'::`21'::_bidSrcFileA[0],
                    294912,
                    `SNI_Packet::~SNI_Packet'::`21'::_bidPtrSA_030_288[0],
                    LastError);
              }
            }
            *((_QWORD *)&v6[7].Next + 1) = 0;
          }
          operator delete(v6, 0xB0u);
        }
      }
    }
    ++v1;
    --v2;
  }
  while ( v2 );
}

```

## disassembly

```asm
0x1801525d0  mov     [rsp+arg_0], rbx
0x1801525d5  mov     [rsp+arg_8], rbp
0x1801525da  mov     [rsp+arg_10], rsi
0x1801525df  push    rdi
0x1801525e0  push    r12
0x1801525e2  push    r13
0x1801525e4  push    r14
0x1801525e6  push    r15
0x1801525e8  sub     rsp, 30h
0x1801525ec  lea     r14, [rcx+8]
0x1801525f0  mov     r15d, 10h
0x1801525f6  xor     r12d, r12d
0x1801525f9  lea     r13, qword_1801ECE38
0x180152600  mov     rax, [r14]
0x180152603  test    rax, rax
0x180152606  jz      short loc_180152632
0x180152608  mov     rbp, [r14]
0x18015260b  mov     edi, r12d
0x18015260e  xchg    ax, ax
0x180152610  mov     eax, edi
0x180152612  lea     rcx, [rax+rax*2]
0x180152616  shl     rcx, 4
0x18015261a  add     rcx, rbp; ListHead
0x18015261d  call    cs:__imp_InterlockedPopEntrySList
0x180152623  mov     rbx, rax
0x180152626  test    rax, rax
0x180152629  jnz     short loc_180152659
0x18015262b  inc     edi
0x18015262d  cmp     edi, 8
0x180152630  jb      short loc_180152610
0x180152632  add     r14, 8
0x180152636  sub     r15, 1
0x18015263a  jnz     short loc_180152600
0x18015263c  mov     rbx, [rsp+58h+arg_0]
0x180152641  mov     rbp, [rsp+58h+arg_8]
0x180152646  mov     rsi, [rsp+58h+arg_10]
0x18015264b  add     rsp, 30h
0x18015264f  pop     r15
0x180152651  pop     r14
0x180152653  pop     r13
0x180152655  pop     r12
0x180152657  pop     rdi
0x180152658  retn
0x180152659  movsxd  rax, dword ptr [rax+94h]
0x180152660  test    eax, eax
0x180152662  jz      short loc_180152697
0x180152664  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x18015266c  jz      short loc_180152697
0x18015266e  mov     r9, rax
0x180152671  mov     rax, cs:off_180248098
0x180152678  mov     [rsp+58h+var_38], r12
0x18015267d  mov     r8d, 5
0x180152683  mov     rdx, cs:?_bidPtrSA_053_261@?3???1SNI_Packet@@AEAA@XZ@4REBDEB; char const * const `SNI_Packet::~SNI_Packet(void)'::`4'::_bidPtrSA_053_261
0x18015268a  mov     rcx, cs:_bidID
0x180152691  call    cs:__guard_dispatch_icall_fptr
0x180152697  mov     [rbx+94h], r12d
0x18015269e  mov     rsi, [rbx+48h]
0x1801526a2  test    rsi, rsi
0x1801526a5  jz      short loc_1801526FE
0x1801526a7  mov     eax, [rbx+8Ch]
0x1801526ad  sub     eax, 3
0x1801526b0  cmp     eax, 1
0x1801526b3  jbe     short loc_1801526FE
0x1801526b5  mov     rcx, [rbx+8]
0x1801526b9  movzx   eax, byte ptr [rbx+80h]
0x1801526c0  mov     r8d, [r13+rax*4+0]
0x1801526c5  mov     rax, [rcx+28h]
0x1801526c9  test    rax, rax
0x1801526cc  jz      short loc_1801526E3
0x1801526ce  mov     r9, [rbx+0A0h]
0x1801526d5  mov     rdx, rsi
0x1801526d8  mov     rcx, [rcx+18h]
0x1801526dc  call    cs:__guard_dispatch_icall_fptr
0x1801526e2  nop
0x1801526e3  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x1801526ea  mov     rax, [rcx]
0x1801526ed  mov     rdx, rsi
0x1801526f0  mov     rax, [rax+80h]
0x1801526f7  call    cs:__guard_dispatch_icall_fptr
0x1801526fd  nop
0x1801526fe  mov     [rbx+48h], r12
0x180152702  mov     [rbx+0A0h], r12
0x180152709  mov     rcx, [rbx+78h]; hObject
0x18015270d  test    rcx, rcx
0x180152710  jz      short loc_180152756
0x180152712  call    cs:__imp_CloseHandle
0x180152718  test    eax, eax
0x18015271a  jnz     short loc_180152752
0x18015271c  call    cs:__imp_GetLastError
0x180152722  test    byte ptr cs:_bidGblFlags, 2
0x180152729  jz      short loc_180152752
0x18015272b  mov     rcx, cs:?_bidPtrSA_030_288@?BF@???1SNI_Packet@@AEAA@XZ@4REB_WEB; wchar_t const * const `SNI_Packet::~SNI_Packet(void)'::`21'::_bidPtrSA_030_288
0x180152732  test    rcx, rcx
0x180152735  jz      short loc_180152752
0x180152737  mov     r9d, eax
0x18015273a  mov     r8, cs:?_bidPtrSA_030_288@?BF@???1SNI_Packet@@AEAA@XZ@4REB_WEB; wchar_t const * const `SNI_Packet::~SNI_Packet(void)'::`21'::_bidPtrSA_030_288
0x180152741  mov     edx, 48000h
0x180152746  mov     rcx, cs:?_bidSrcFileA@?BF@???1SNI_Packet@@AEAA@XZ@4REBDEB; char const * const `SNI_Packet::~SNI_Packet(void)'::`21'::_bidSrcFileA
0x18015274d  call    _bidTraceW
0x180152752  mov     [rbx+78h], r12
0x180152756  mov     edx, 0B0h; unsigned __int64
0x18015275b  mov     rcx, rbx; void *
0x18015275e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180152763  jmp     loc_180152610
```
