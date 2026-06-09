# __ExceptionPtr::_CopyException(void const *,_s_ThrowInfo const *,bool)

- ea: `0x180017fec`
- end: `0x1800181de`
- name: `?_CopyException@__ExceptionPtr@@SA?AV?$shared_ptr@V__ExceptionPtr@@@std@@PEBXPEBU_s_ThrowInfo@@_N@Z`
- size: `498`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180017660`
- `0x180018474`

## callees

- `0x18000b680`
- `0x180017854`
- `0x1800178e0`
- `0x180017970`
- `0x180017b08`
- `0x180017fec`
- `0x18001c850`
- `0x18001d568`
- `0x18007d020`

## import_xrefs

- `ntdll!RtlPcToFileHeader` at `0x180018072`
- `ntdll!RtlPcToFileHeader` at `0x180018072`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall __ExceptionPtr::_CopyException(__int64 a1, _QWORD *a2, ThrowInfo *a3, char a4)
{
  ThrowInfo *v5; // rbx
  PVOID v7; // rax
  __ExceptionPtr *v8; // rax
  __ExceptionPtr *v9; // rax
  __ExceptionPtr *v10; // rax
  volatile signed __int32 *v11; // rbx
  __int64 result; // rax
  __int128 v13; // [rsp+28h] [rbp-B0h] BYREF
  EHExceptionRecord v14; // [rsp+40h] [rbp-98h] BYREF
  __int64 v15; // [rsp+80h] [rbp-58h]
  _BYTE pExceptionObject[24]; // [rsp+88h] [rbp-50h] BYREF
  _QWORD v17[7]; // [rsp+A0h] [rbp-38h] BYREF
  PVOID BaseOfImage; // [rsp+E8h] [rbp+10h] BYREF
  __ExceptionPtr *v20; // [rsp+F0h] [rbp+18h]
  char v21; // [rsp+F8h] [rbp+20h] BYREF

  v15 = -2;
  v5 = a3;
  *(_QWORD *)&v14.NumberParameters = 4;
  *(_QWORD *)&v14.params.magicNumber = 429065504;
  v14.ExceptionCode = -529697949;
  v14.ExceptionFlags = 1;
  v14.ExceptionRecord = 0;
  v14.ExceptionAddress = 0;
  v14.params.pExceptionObject = a2;
  if ( a3 && (a3->attributes & 0x10) != 0 )
    v5 = *(ThrowInfo **)(*(_QWORD *)(*a2 - 8LL) + 48LL);
  v14.params.pThrowInfo = v5;
  v7 = RtlPcToFileHeader(v5, &BaseOfImage);
  BaseOfImage = v7;
  v14.params.pThrowImageBase = v7;
  if ( v5 && ((v5->attributes & 8) != 0 || !v7) )
    v14.params.magicNumber = 26820608;
  try
  {
    v13 = 0;
    if ( a4 )
    {
      v8 = (__ExceptionPtr *)operator new(0xA0u);
      v20 = v8;
      if ( v8 )
        v8 = __ExceptionPtr::__ExceptionPtr(v8, &v14, 1);
      std::shared_ptr<__ExceptionPtr>::reset<__ExceptionPtr>(&v13, v8);
    }
    else
    {
      v9 = (__ExceptionPtr *)malloc_crt(0xA0u);
      if ( !v9 )
      {
        std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
        throw (std::bad_alloc *)pExceptionObject;
      }
      v20 = (__ExceptionPtr *)&v21;
      v10 = __ExceptionPtr::__ExceptionPtr(v9, &v14, 0);
      std::shared_ptr<__ExceptionPtr>::reset<__ExceptionPtr,void (*)(__ExceptionPtr *),_DebugMallocator<int>>(
        &v13,
        v10,
        _DeleteExceptionPtr,
        &v21,
        0);
    }
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    if ( (__int128 *)a1 == &v13 )
    {
      v11 = (volatile signed __int32 *)*((_QWORD *)&v13 + 1);
    }
    else
    {
      *(_OWORD *)a1 = v13;
      v11 = 0;
    }
    if ( v11 )
    {
      if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
        if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
      }
    }
    result = a1;
  }
  catch ( std::bad_alloc v17 )
  {
    __ExceptionPtr::_BadAllocException(a1);
    v17[0] = &std::bad_alloc::`vftable';
    exception::~exception((exception *)v17);
    return a1;
  }
  catch ( ... )
  {
    terminate();
  }
  return result;
}

```

## disassembly

```asm
0x180017fec  mov     rax, rsp
0x180017fef  mov     [rax+8], rcx
0x180017ff3  push    rbx
0x180017ff4  push    rsi
0x180017ff5  push    rdi
0x180017ff6  sub     rsp, 0C0h
0x180017ffd  mov     qword ptr [rax-58h], 0FFFFFFFFFFFFFFFEh
0x180018005  mov     sil, r9b
0x180018008  mov     rbx, r8
0x18001800b  mov     rdi, rcx
0x18001800e  mov     [rsp+0D8h+var_B8], 0
0x180018016  mov     qword ptr [rax-80h], 4
0x18001801e  mov     qword ptr [rax-78h], 19930520h
0x180018026  mov     [rsp+0D8h+var_98.ExceptionCode], 0E06D7363h
0x18001802e  mov     [rsp+0D8h+var_98.ExceptionFlags], 1
0x180018036  mov     [rsp+0D8h+var_98.ExceptionRecord], 0
0x18001803f  mov     [rsp+0D8h+var_98.ExceptionAddress], 0
0x180018048  mov     [rax-70h], rdx
0x18001804c  test    rbx, rbx
0x18001804f  jz      short loc_180018062
0x180018051  test    byte ptr [r8], 10h
0x180018055  jz      short loc_180018062
0x180018057  mov     rax, [rdx]
0x18001805a  mov     rcx, [rax-8]
0x18001805e  mov     rbx, [rcx+30h]
0x180018062  mov     [rsp+0D8h+var_98.params.pThrowInfo], rbx
0x180018067  lea     rdx, [rsp+0D8h+BaseOfImage]; BaseOfImage
0x18001806f  mov     rcx, rbx; PcValue
0x180018072  call    cs:__imp_RtlPcToFileHeader
0x180018078  mov     [rsp+0D8h+BaseOfImage], rax
0x180018080  mov     [rsp+0D8h+var_98.params.pThrowImageBase], rax
0x180018085  test    rbx, rbx
0x180018088  jz      short loc_18001809C
0x18001808a  test    byte ptr [rbx], 8
0x18001808d  jnz     short loc_180018094
0x18001808f  test    rax, rax
0x180018092  jnz     short loc_18001809C
0x180018094  mov     [rsp+0D8h+var_98.params.magicNumber], 1994000h
0x18001809c  xorps   xmm0, xmm0
0x18001809f  movdqu  [rsp+0D8h+var_B0], xmm0
0x1800180a5  mov     ecx, 0A0h; Size
0x1800180aa  test    sil, sil
0x1800180ad  jz      short loc_1800180E1
0x1800180af  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800180b4  mov     [rsp+0D8h+arg_10], rax
0x1800180bc  test    rax, rax
0x1800180bf  jz      short loc_1800180D2
0x1800180c1  mov     r8b, 1; bool
0x1800180c4  lea     rdx, [rsp+0D8h+var_98]; struct EHExceptionRecord *
0x1800180c9  mov     rcx, rax; this
0x1800180cc  call    ??0__ExceptionPtr@@AEAA@PEBUEHExceptionRecord@@_N@Z; __ExceptionPtr::__ExceptionPtr(EHExceptionRecord const *,bool)
0x1800180d1  nop
0x1800180d2  mov     rdx, rax
0x1800180d5  lea     rcx, [rsp+0D8h+var_B0]
0x1800180da  call    ??$reset@V__ExceptionPtr@@@?$shared_ptr@V__ExceptionPtr@@@std@@QEAAXPEAV__ExceptionPtr@@@Z; std::shared_ptr<__ExceptionPtr>::reset<__ExceptionPtr>(__ExceptionPtr *)
0x1800180df  jmp     short loc_18001812C
0x1800180e1  call    _malloc_crt
0x1800180e6  test    rax, rax
0x1800180e9  jz      loc_1800181BB
0x1800180ef  lea     rcx, [rsp+0D8h+arg_18]
0x1800180f7  mov     [rsp+0D8h+arg_10], rcx
0x1800180ff  xor     r8d, r8d; bool
0x180018102  lea     rdx, [rsp+0D8h+var_98]; struct EHExceptionRecord *
0x180018107  mov     rcx, rax; this
0x18001810a  call    ??0__ExceptionPtr@@AEAA@PEBUEHExceptionRecord@@_N@Z; __ExceptionPtr::__ExceptionPtr(EHExceptionRecord const *,bool)
0x18001810f  nop
0x180018110  lea     r9, [rsp+0D8h+arg_18]
0x180018118  lea     r8, ?_DeleteExceptionPtr@@YAXQEAV__ExceptionPtr@@@Z; _DeleteExceptionPtr(__ExceptionPtr * const)
0x18001811f  mov     rdx, rax
0x180018122  lea     rcx, [rsp+0D8h+var_B0]
0x180018127  call    ??$reset@V__ExceptionPtr@@P6AXPEAV1@@ZV?$_DebugMallocator@H@@@?$shared_ptr@V__ExceptionPtr@@@std@@QEAAXPEAV__ExceptionPtr@@P6AX0@ZV?$_DebugMallocator@H@@@Z; std::shared_ptr<__ExceptionPtr>::reset<__ExceptionPtr,void (*)(__ExceptionPtr *),_DebugMallocator<int>>(__ExceptionPtr *,void (*)(__ExceptionPtr *),_DebugMallocator<int>)
0x18001812c  mov     qword ptr [rdi], 0
0x180018133  mov     qword ptr [rdi+8], 0
0x18001813b  lea     rax, [rsp+0D8h+var_B0]
0x180018140  cmp     rdi, rax
0x180018143  jz      short loc_18001815A
0x180018145  mov     rax, qword ptr [rsp+0D8h+var_B0+8]
0x18001814a  mov     [rdi+8], rax
0x18001814e  xor     ebx, ebx
0x180018150  mov     rax, qword ptr [rsp+0D8h+var_B0]
0x180018155  mov     [rdi], rax
0x180018158  jmp     short loc_18001815F
0x18001815a  mov     rbx, qword ptr [rsp+0D8h+var_B0+8]
0x18001815f  mov     [rsp+0D8h+var_B8], 1
0x180018167  test    rbx, rbx
0x18001816a  jz      short loc_1800181A3
0x18001816c  or      esi, 0FFFFFFFFh
0x18001816f  mov     eax, esi
0x180018171  lock xadd [rbx+8], eax
0x180018176  add     eax, esi
0x180018178  jnz     short loc_1800181A3
0x18001817a  mov     rax, [rbx]
0x18001817d  mov     rcx, rbx
0x180018180  mov     rax, [rax]
0x180018183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018188  mov     eax, esi
0x18001818a  lock xadd [rbx+0Ch], eax
0x18001818f  add     eax, esi
0x180018191  jnz     short loc_1800181A3
0x180018193  mov     rax, [rbx]
0x180018196  mov     rcx, rbx
0x180018199  mov     rax, [rax+8]
0x18001819d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800181a2  nop
0x1800181a3  mov     rax, rdi
0x1800181a6  jmp     short loc_1800181B0
0x1800181a8  mov     rax, [rsp+0D8h+arg_0]
0x1800181b0  add     rsp, 0C0h
0x1800181b7  pop     rdi
0x1800181b8  pop     rsi
0x1800181b9  pop     rbx
0x1800181ba  retn
0x1800181bb  lea     rcx, [rsp+0D8h+pExceptionObject]; this
0x1800181c3  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x1800181c8  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800181cf  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x1800181d7  call    _CxxThrowException
```
