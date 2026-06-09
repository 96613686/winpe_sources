# CFLACSource::OnMetadataBufferRead(IMFAsyncResult *)

- ea: `0x1800244f0`
- end: `0x18002460d`
- name: `?OnMetadataBufferRead@CFLACSource@@QEAAJPEAUIMFAsyncResult@@@Z`
- size: `285`
- prototype: `__int64 __fastcall(CFLACSource *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180023ed0`

## callees

- `0x180020398`
- `0x180020484`
- `0x1800230b8`
- `0x1800244f0`
- `0x180027338`
- `0x180027da0`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800245d3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800245d3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFLACSource::OnMetadataBufferRead(CFLACSource *this, struct IMFAsyncResult *a2)
{
  int v4; // ecx
  __int64 v5; // rdx
  int v6; // eax
  __int64 result; // rax
  int v8; // [rsp+60h] [rbp+20h]
  unsigned int v9; // [rsp+70h] [rbp+30h] BYREF
  __int64 v10; // [rsp+78h] [rbp+38h] BYREF

  v9 = 0;
  v10 = 0;
  if ( *((_DWORD *)this + 56) == 5 )
  {
    v8 = -1072873851;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_12;
    v5 = 132;
    goto LABEL_4;
  }
  ((void (__fastcall *)(struct IMFAsyncResult *, __int64 *))a2->lpVtbl->GetState)(a2, &v10);
  v8 = (*(__int64 (__fastcall **)(_QWORD, struct IMFAsyncResult *, unsigned int *))(**((_QWORD **)this + 39) + 88LL))(
         *((_QWORD *)this + 39),
         a2,
         &v9);
  if ( v8 >= 0 )
  {
    if ( v9 )
      v6 = CBuffReader::MoveEnd((CFLACSource *)((char *)this + 328), v9);
    else
      v6 = CFLACSource::EndOfStream(this);
    v8 = v6;
  }
  else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v5 = 133;
LABEL_4:
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, &WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids, this, v4);
  }
LABEL_12:
  SetEvent(*((HANDLE *)this + 50));
  result = (unsigned int)v8;
  if ( v8 < 0 )
  {
    CFLACSource::StreamingError(this, v8);
    result = (unsigned int)v8;
  }
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    return (unsigned int)v8;
  }
  return result;
}

```

## disassembly

```asm
0x1800244f0  push    rbp
0x1800244f2  push    rbx
0x1800244f3  push    rdi
0x1800244f4  mov     rbp, rsp
0x1800244f7  sub     rsp, 40h
0x1800244fb  mov     rdi, rdx
0x1800244fe  mov     rbx, rcx
0x180024501  mov     [rbp+var_10], rcx
0x180024505  lea     rax, [rbp+arg_0]
0x180024509  mov     [rbp+var_8], rax
0x18002450d  mov     [rbp+arg_10], 0
0x180024514  mov     [rbp+arg_18], 0
0x18002451c  cmp     dword ptr [rcx+0E0h], 5
0x180024523  jnz     short loc_18002455F
0x180024525  mov     ecx, 0C00D3E85h
0x18002452a  mov     [rbp+arg_0], ecx
0x18002452d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180024532  cmp     al, 1
0x180024534  jb      loc_1800245CC
0x18002453a  mov     edx, 84h
0x18002453f  mov     [rsp+40h+var_20], ecx
0x180024543  mov     r9, rbx
0x180024546  lea     r8, WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids
0x18002454d  mov     rcx, cs:WPP_GLOBAL_Control
0x180024554  mov     rcx, [rcx+10h]
0x180024558  call    WPP_SF_qd
0x18002455d  jmp     short loc_1800245CC
0x18002455f  mov     [rbp+arg_0], 0
0x180024566  mov     rax, [rdx]
0x180024569  lea     rdx, [rbp+arg_18]
0x18002456d  mov     rcx, rdi
0x180024570  mov     rax, [rax+18h]
0x180024574  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024579  mov     rcx, [rbx+138h]
0x180024580  mov     rax, [rcx]
0x180024583  lea     r8, [rbp+arg_10]
0x180024587  mov     rdx, rdi
0x18002458a  mov     rax, [rax+58h]
0x18002458e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024593  mov     ecx, eax
0x180024595  mov     [rbp+arg_0], eax
0x180024598  test    eax, eax
0x18002459a  jns     short loc_1800245AC
0x18002459c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800245a1  cmp     al, 1
0x1800245a3  jb      short loc_1800245CC
0x1800245a5  mov     edx, 85h
0x1800245aa  jmp     short loc_18002453F
0x1800245ac  mov     edx, [rbp+arg_10]; unsigned int
0x1800245af  test    edx, edx
0x1800245b1  jnz     short loc_1800245BD
0x1800245b3  mov     rcx, rbx; this
0x1800245b6  call    ?EndOfStream@CFLACSource@@AEAAJXZ; CFLACSource::EndOfStream(void)
0x1800245bb  jmp     short loc_1800245C9
0x1800245bd  lea     rcx, [rbx+148h]; this
0x1800245c4  call    ?MoveEnd@CBuffReader@@QEAAJK@Z; CBuffReader::MoveEnd(ulong)
0x1800245c9  mov     [rbp+arg_0], eax
0x1800245cc  mov     rcx, [rbx+190h]; hEvent
0x1800245d3  call    cs:__imp_SetEvent
0x1800245d9  mov     eax, [rbp+arg_0]
0x1800245dc  test    eax, eax
0x1800245de  jns     short loc_1800245ED
0x1800245e0  mov     edx, eax; int
0x1800245e2  mov     rcx, rbx; this
0x1800245e5  call    ?StreamingError@CFLACSource@@AEAAXJ@Z; CFLACSource::StreamingError(long)
0x1800245ea  mov     eax, [rbp+arg_0]
0x1800245ed  mov     rcx, [rbp+arg_18]
0x1800245f1  test    rcx, rcx
0x1800245f4  jz      short loc_180024605
0x1800245f6  mov     rax, [rcx]
0x1800245f9  mov     rax, [rax+10h]
0x1800245fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024602  mov     eax, [rbp+arg_0]
0x180024605  add     rsp, 40h
0x180024609  pop     rdi
0x18002460a  pop     rbx
0x18002460b  pop     rbp
0x18002460c  retn
```
