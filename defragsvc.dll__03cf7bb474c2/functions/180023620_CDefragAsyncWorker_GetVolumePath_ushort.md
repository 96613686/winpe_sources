# CDefragAsyncWorker::GetVolumePath(ushort * *)

- ea: `0x180023620`
- end: `0x180023700`
- name: `?GetVolumePath@CDefragAsyncWorker@@UEAAJPEAPEAG@Z`
- size: `224`
- prototype: `__int64 __fastcall(CDefragAsyncWorker *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180023620`
- `0x180023708`
- `0x180067b0a`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800236aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800236aa`

## string_xrefs

- `0x18002363d`: `CDefragAsyncWorker::GetVolumePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDefragAsyncWorker::GetVolumePath(CDefragAsyncWorker *this, unsigned __int16 **a2)
{
  __int16 v4; // ax
  unsigned int v5; // ebx
  unsigned int v7; // ebp
  unsigned __int16 *v8; // rcx
  int v9; // [rsp+20h] [rbp-68h] BYREF
  __int16 v10; // [rsp+24h] [rbp-64h]
  __int16 v11; // [rsp+26h] [rbp-62h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v9, "CDefragAsyncWorker::GetVolumePath", 960, 1);
  v4 = 964;
  if ( !a2 )
  {
    v9 = -2147024809;
LABEL_3:
    v11 = v4;
    goto LABEL_4;
  }
  *a2 = 0;
  v9 = 0;
  v10 = 964;
  v7 = *((_DWORD *)this + 54) + 1;
  v8 = (unsigned __int16 *)CoTaskMemAlloc(2LL * v7);
  *a2 = v8;
  v4 = 968;
  if ( !v8 )
  {
    v9 = -2147024882;
    goto LABEL_3;
  }
  v9 = 0;
  v10 = 968;
  memset_0(v8, 0, 2LL * v7);
  if ( v7 > 1 )
    StringCchCopyW(*a2, v7, *((const unsigned __int16 **)this + 26));
LABEL_4:
  v5 = v9;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v9);
  return v5;
}

```

## disassembly

```asm
0x180023620  push    rbx
0x180023622  push    rbp
0x180023623  push    rsi
0x180023624  push    rdi
0x180023625  push    r14
0x180023627  sub     rsp, 60h
0x18002362b  mov     rbx, rdx
0x18002362e  mov     rdi, rcx
0x180023631  mov     r9d, 1; unsigned __int16
0x180023637  mov     r8d, 3C0h; unsigned __int16
0x18002363d  lea     rdx, aCdefragasyncwo_32; "CDefragAsyncWorker::GetVolumePath"
0x180023644  lea     rcx, [rsp+88h+var_68]; this
0x180023649  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002364e  nop
0x18002364f  mov     eax, 3C4h
0x180023654  test    rbx, rbx
0x180023657  jnz     short loc_180023681
0x180023659  mov     [rsp+88h+var_68], 80070057h
0x180023661  mov     [rsp+88h+var_62], ax
0x180023666  mov     ebx, [rsp+88h+var_68]
0x18002366a  lea     rcx, [rsp+88h+var_68]; this
0x18002366f  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180023674  mov     eax, ebx
0x180023676  add     rsp, 60h
0x18002367a  pop     r14
0x18002367c  pop     rdi
0x18002367d  pop     rsi
0x18002367e  pop     rbp
0x18002367f  pop     rbx
0x180023680  retn
0x180023681  mov     qword ptr [rbx], 0
0x180023688  mov     [rsp+88h+var_68], 0
0x180023690  mov     [rsp+88h+var_64], ax
0x180023695  mov     ebp, [rdi+0D8h]
0x18002369b  inc     ebp
0x18002369d  mov     esi, ebp
0x18002369f  lea     r14, ds:0[rbp*2]
0x1800236a7  mov     rcx, r14; cb
0x1800236aa  call    cs:__imp_CoTaskMemAlloc
0x1800236b0  mov     rcx, rax; void *
0x1800236b3  mov     [rbx], rax
0x1800236b6  test    rax, rax
0x1800236b9  mov     eax, 3C8h
0x1800236be  jz      short loc_1800236F2
0x1800236c0  mov     [rsp+88h+var_68], 0
0x1800236c8  mov     [rsp+88h+var_64], ax
0x1800236cd  mov     r8, r14; Size
0x1800236d0  xor     edx, edx; Val
0x1800236d2  call    memset_0
0x1800236d7  cmp     ebp, 1
0x1800236da  jbe     short loc_180023666
0x1800236dc  mov     r8, [rdi+0D0h]; unsigned __int16 *
0x1800236e3  mov     edx, esi; unsigned __int64
0x1800236e5  mov     rcx, [rbx]; unsigned __int16 *
0x1800236e8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800236ed  jmp     loc_180023666
0x1800236f2  mov     [rsp+88h+var_68], 8007000Eh
0x1800236fa  jmp     loc_180023661
```
