# CFreeSlabManagerDelegate::MarkSlabMoveFrom(ulong)

- ea: `0x1800603b0`
- end: `0x180060467`
- name: `?MarkSlabMoveFrom@CFreeSlabManagerDelegate@@UEAAJK@Z`
- size: `183`
- prototype: `__int64 __fastcall(CFreeSlabManagerDelegate *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x1800603b0`
- `0x18006a010`

## import_xrefs

- `ntdll!RtlRbRemoveNode` at `0x180060429`
- `ntdll!RtlRbRemoveNode` at `0x180060429`

## string_xrefs

- `0x1800603be`: `CFreeSlabManagerDelegate::MarkSlabMoveFrom`

## pseudocode

```c
__int64 __fastcall CFreeSlabManagerDelegate::MarkSlabMoveFrom(CFreeSlabManagerDelegate *this, unsigned int a2)
{
  __int64 v2; // rsi
  unsigned int v4; // ebx
  __int64 v5; // rbp
  __int64 v6; // rdi
  int v8; // [rsp+20h] [rbp-68h] BYREF
  __int16 v9; // [rsp+24h] [rbp-64h]
  __int16 v10; // [rsp+26h] [rbp-62h]

  v2 = a2;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v8, "CFreeSlabManagerDelegate::MarkSlabMoveFrom", 441, 1);
  if ( (unsigned int)v2 < *((_DWORD *)this + 36) )
  {
    v5 = *((_QWORD *)this + 9);
    v6 = v2 << 6;
    v8 = 0;
    v9 = 443;
    if ( (*(_BYTE *)((v2 << 6) + v5 + 56) & 1) != 0 )
    {
      RtlRbRemoveNode((char *)this + 280, v6 + v5 + 32);
      (*(void (__fastcall **)(CFreeSlabManagerDelegate *, _QWORD))(*(_QWORD *)this + 224LL))(this, (unsigned int)v2);
      *(_BYTE *)(v6 + v5 + 56) &= ~1u;
      --*((_DWORD *)this + 74);
      v4 = v8;
    }
    else
    {
      v4 = 0;
    }
  }
  else
  {
    v4 = -2147024809;
    v10 = 443;
    v8 = -2147024809;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v8);
  return v4;
}

```

## disassembly

```asm
0x1800603b0  push    rbx
0x1800603b2  push    rbp
0x1800603b3  push    rsi
0x1800603b4  push    rdi
0x1800603b5  sub     rsp, 68h
0x1800603b9  mov     esi, edx
0x1800603bb  mov     rbx, rcx
0x1800603be  lea     rdx, aCfreeslabmanag_30; "CFreeSlabManagerDelegate::MarkSlabMoveF"...
0x1800603c5  mov     r9d, 1; unsigned __int16
0x1800603cb  lea     rcx, [rsp+88h+var_68]; this
0x1800603d0  mov     r8d, 1B9h; unsigned __int16
0x1800603d6  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800603db  mov     eax, 1BBh
0x1800603e0  cmp     esi, [rbx+90h]
0x1800603e6  jb      short loc_1800603F8
0x1800603e8  mov     ebx, 80070057h
0x1800603ed  mov     [rsp+88h+var_62], ax
0x1800603f2  mov     [rsp+88h+var_68], ebx
0x1800603f6  jmp     short loc_180060452
0x1800603f8  mov     rbp, [rbx+48h]
0x1800603fc  mov     rdi, rsi
0x1800603ff  shl     rdi, 6
0x180060403  mov     [rsp+88h+var_68], 0
0x18006040b  mov     [rsp+88h+var_64], ax
0x180060410  test    byte ptr [rdi+rbp+38h], 1
0x180060415  jnz     short loc_18006041B
0x180060417  xor     ebx, ebx
0x180060419  jmp     short loc_180060452
0x18006041b  lea     rdx, [rbp+20h]
0x18006041f  add     rdx, rdi
0x180060422  lea     rcx, [rbx+118h]
0x180060429  call    cs:__imp_RtlRbRemoveNode
0x18006042f  mov     rax, [rbx]
0x180060432  mov     edx, esi
0x180060434  mov     rcx, rbx
0x180060437  mov     rax, [rax+0E0h]
0x18006043e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060443  and     byte ptr [rdi+rbp+38h], 0FEh
0x180060448  dec     dword ptr [rbx+128h]
0x18006044e  mov     ebx, [rsp+88h+var_68]
0x180060452  lea     rcx, [rsp+88h+var_68]; this
0x180060457  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18006045c  mov     eax, ebx
0x18006045e  add     rsp, 68h
0x180060462  pop     rdi
0x180060463  pop     rsi
0x180060464  pop     rbp
0x180060465  pop     rbx
0x180060466  retn
```
