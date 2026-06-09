# InitializeCellHeap(void)

- ea: `0x18009fa24`
- end: `0x18009fae3`
- name: `?InitializeCellHeap@@YAJXZ`
- size: `191`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002499c`

## callees

- `0x180021e70`
- `0x180022870`
- `0x18009fa24`
- `0x1800a4758`
- `0x1800b7ca4`

## import_xrefs

- `ntdll!RtlGetAppContainerNamedObjectPath` at `0x18009fa4d`
- `ntdll!RtlGetAppContainerNamedObjectPath` at `0x18009fa4d`
- `ntdll!RtlFreeUnicodeString` at `0x18009facb`
- `ntdll!RtlFreeUnicodeString` at `0x18009facb`

## pseudocode

```c
__int64 InitializeCellHeap(void)
{
  unsigned int v0; // ebx
  CellHeap *v1; // rax
  struct CellHeap *v2; // rax
  struct CellHeap *v3; // rdi
  struct _UNICODE_STRING UnicodeString; // [rsp+20h] [rbp-18h] BYREF
  int v6; // [rsp+40h] [rbp+8h] BYREF

  v0 = 0;
  v6 = 0;
  UnicodeString = 0;
  if ( (int)RtlGetAppContainerNamedObjectPath(0, 0, 0, &UnicodeString) < 0 || UnicodeString.Length )
  {
    v0 = 1764;
    goto LABEL_11;
  }
  if ( !g_pCellHeap )
  {
    v1 = (CellHeap *)AllocWrapper(0x88u);
    if ( v1 )
    {
      v2 = CellHeap::CellHeap(v1, &v6);
      g_pCellHeap = v2;
      v3 = v2;
      if ( v2 )
      {
        v0 = v6;
        if ( v6 )
        {
          CellHeap::~CellHeap(v2);
          FreeWrapper(v3);
          g_pCellHeap = 0;
        }
        goto LABEL_11;
      }
    }
    else
    {
      g_pCellHeap = 0;
    }
    v0 = 14;
  }
LABEL_11:
  RtlFreeUnicodeString(&UnicodeString);
  return v0;
}

```

## disassembly

```asm
0x18009fa24  mov     rax, rsp
0x18009fa27  mov     [rax+10h], rbx
0x18009fa2b  mov     [rax+18h], rsi
0x18009fa2f  push    rdi
0x18009fa30  sub     rsp, 30h
0x18009fa34  xorps   xmm0, xmm0
0x18009fa37  lea     r9, [rax-18h]
0x18009fa3b  xor     esi, esi
0x18009fa3d  xor     r8d, r8d
0x18009fa40  mov     ebx, esi
0x18009fa42  xor     edx, edx
0x18009fa44  xor     ecx, ecx
0x18009fa46  mov     [rax+8], ebx
0x18009fa49  movups  xmmword ptr [rax-18h], xmm0
0x18009fa4d  call    cs:__imp_RtlGetAppContainerNamedObjectPath
0x18009fa53  test    eax, eax
0x18009fa55  js      short loc_18009FAC1
0x18009fa57  cmp     [rsp+38h+UnicodeString.Length], si
0x18009fa5c  jnz     short loc_18009FAC1
0x18009fa5e  cmp     cs:?g_pCellHeap@@3PEAVCellHeap@@EA, rsi; CellHeap * g_pCellHeap
0x18009fa65  jnz     short loc_18009FAC6
0x18009fa67  mov     ecx, 88h; dwBytes
0x18009fa6c  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x18009fa71  test    rax, rax
0x18009fa74  jz      short loc_18009FAB3
0x18009fa76  lea     rdx, [rsp+38h+arg_0]; int *
0x18009fa7b  mov     rcx, rax; this
0x18009fa7e  call    ??0CellHeap@@QEAA@PEAJ@Z; CellHeap::CellHeap(long *)
0x18009fa83  mov     cs:?g_pCellHeap@@3PEAVCellHeap@@EA, rax; CellHeap * g_pCellHeap
0x18009fa8a  mov     rdi, rax
0x18009fa8d  test    rax, rax
0x18009fa90  jz      short loc_18009FABA
0x18009fa92  mov     ebx, [rsp+38h+arg_0]
0x18009fa96  test    ebx, ebx
0x18009fa98  jz      short loc_18009FAC6
0x18009fa9a  mov     rcx, rax; this
0x18009fa9d  call    ??1CellHeap@@QEAA@XZ; CellHeap::~CellHeap(void)
0x18009faa2  mov     rcx, rdi; lpMem
0x18009faa5  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18009faaa  mov     cs:?g_pCellHeap@@3PEAVCellHeap@@EA, rsi; CellHeap * g_pCellHeap
0x18009fab1  jmp     short loc_18009FAC6
0x18009fab3  mov     cs:?g_pCellHeap@@3PEAVCellHeap@@EA, rsi; CellHeap * g_pCellHeap
0x18009faba  mov     ebx, 0Eh
0x18009fabf  jmp     short loc_18009FAC6
0x18009fac1  mov     ebx, 6E4h
0x18009fac6  lea     rcx, [rsp+38h+UnicodeString]; UnicodeString
0x18009facb  call    cs:__imp_RtlFreeUnicodeString
0x18009fad1  mov     rsi, [rsp+38h+arg_10]
0x18009fad6  mov     eax, ebx
0x18009fad8  mov     rbx, [rsp+38h+arg_8]
0x18009fadd  add     rsp, 30h
0x18009fae1  pop     rdi
0x18009fae2  retn
```
