# ThreadProcHelper::CreateInstance(ThreadProcWorkType,void *,IThreadProcHelper * *)

- ea: `0x180007b38`
- end: `0x180007c68`
- name: `?CreateInstance@ThreadProcHelper@@SAJW4ThreadProcWorkType@@PEAXPEAPEAUIThreadProcHelper@@@Z`
- size: `304`
- prototype: `__int64 __fastcall(__int64, void *, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b520`

## callees

- `0x180007114`
- `0x18000763c`
- `0x180007b14`
- `0x180007b38`
- `0x1800081e4`
- `0x18001f1d0`
- `0x18001ffb0`
- `0x180045010`

## string_xrefs

- `0x180007bc9`: `multimedia\dshow\filters.ks\ksproxy\capabilityhelpers\lib\threadprochelper.cpp`
- `0x180007c13`: `multimedia\dshow\filters.ks\ksproxy\capabilityhelpers\lib\threadprochelper.cpp`
- `0x180007c46`: `multimedia\dshow\filters.ks\ksproxy\capabilityhelpers\lib\threadprochelper.cpp`

## pseudocode

```c
__int64 __fastcall ThreadProcHelper::CreateInstance(__int64 a1, void *a2, _QWORD *a3)
{
  unsigned int v5; // ebx
  __int64 v6; // rdx
  ThreadProcHelper *v7; // rax
  ThreadProcHelper *v8; // rbx
  ThreadProcHelper *v9; // rax
  __int64 v10; // rbx
  __int64 v11; // rdx
  int v12; // eax
  unsigned int v13; // esi
  int v15; // eax
  int v16; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  ThreadProcHelper *v18; // [rsp+40h] [rbp+18h] BYREF

  if ( !a3 )
  {
    v5 = -2147467261;
    v6 = 17;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\threadprochelper.cpp",
      (const char *)v5,
      v16);
    return v5;
  }
  *a3 = 0;
  v7 = (ThreadProcHelper *)operator new(0x68u);
  v8 = v7;
  if ( !v7 || (memset_0(v7, 0, 0x68u), v9 = ThreadProcHelper::ThreadProcHelper(v8), v18 = v9, (v10 = (__int64)v9) == 0) )
  {
    v5 = -2147024882;
    v6 = 21;
    goto LABEL_12;
  }
  (*(void (__fastcall **)(ThreadProcHelper *))(*(_QWORD *)v9 + 8LL))(v9);
  v12 = ThreadProcHelper::InternalInitialize(v10, v11, a2);
  v13 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16,
      (unsigned int)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\threadprochelper.cpp",
      (const char *)(unsigned int)v12,
      v16);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    return v13;
  }
  v15 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v10)(
          v10,
          &GUID_0beaa6cc_1392_4e3c_b0df_51b861bd6c6e,
          a3);
  v5 = v15;
  if ( v15 >= 0 )
    v5 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18,
      (unsigned int)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\threadprochelper.cpp",
      (const char *)(unsigned int)v15,
      v16);
  wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>((__int64 *)&v18);
  return v5;
}

```

## disassembly

```asm
0x180007b38  mov     [rsp+arg_0], rbx
0x180007b3d  mov     [rsp+arg_8], rsi
0x180007b42  push    rdi; int
0x180007b43  sub     rsp, 20h
0x180007b47  mov     rdi, r8
0x180007b4a  mov     rsi, rdx
0x180007b4d  test    r8, r8
0x180007b50  jnz     short loc_180007B60
0x180007b52  mov     ebx, 80004003h
0x180007b57  lea     edx, [r8+11h]
0x180007b5b  jmp     loc_180007C41
0x180007b60  mov     ecx, 68h ; 'h'; Size
0x180007b65  mov     qword ptr [r8], 0
0x180007b6c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007b71  mov     rbx, rax
0x180007b74  test    rax, rax
0x180007b77  jz      loc_180007C37
0x180007b7d  xor     edx, edx; Val
0x180007b7f  mov     rcx, rax; void *
0x180007b82  lea     r8d, [rdx+68h]; Size
0x180007b86  call    memset_0
0x180007b8b  mov     rcx, rbx; this
0x180007b8e  call    ??0ThreadProcHelper@@IEAA@XZ; ThreadProcHelper::ThreadProcHelper(void)
0x180007b93  mov     [rsp+28h+arg_10], rax
0x180007b98  mov     rbx, rax
0x180007b9b  test    rax, rax
0x180007b9e  jz      loc_180007C37
0x180007ba4  mov     rcx, [rax]
0x180007ba7  mov     rax, [rcx+8]
0x180007bab  mov     rcx, rbx
0x180007bae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bb3  mov     r8, rsi
0x180007bb6  mov     rcx, rbx
0x180007bb9  call    ?InternalInitialize@ThreadProcHelper@@IEAAJW4ThreadProcWorkType@@PEAX@Z; ThreadProcHelper::InternalInitialize(ThreadProcWorkType,void *)
0x180007bbe  mov     esi, eax
0x180007bc0  test    eax, eax
0x180007bc2  jns     short loc_180007BF0
0x180007bc4  mov     rcx, [rsp+28h]; this
0x180007bc9  lea     r8, aMultimediaDsho_3; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x180007bd0  mov     r9d, eax; char *
0x180007bd3  mov     edx, 16h; void *
0x180007bd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007bdd  mov     rcx, [rbx]
0x180007be0  mov     rax, [rcx+10h]
0x180007be4  mov     rcx, rbx
0x180007be7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bec  mov     eax, esi
0x180007bee  jmp     short loc_180007C57
0x180007bf0  mov     rax, [rbx]
0x180007bf3  lea     rdx, _GUID_0beaa6cc_1392_4e3c_b0df_51b861bd6c6e
0x180007bfa  mov     r8, rdi
0x180007bfd  mov     rcx, rbx
0x180007c00  mov     rax, [rax]
0x180007c03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c08  mov     ebx, eax
0x180007c0a  test    eax, eax
0x180007c0c  jns     short loc_180007C29
0x180007c0e  mov     rcx, [rsp+28h]; this
0x180007c13  lea     r8, aMultimediaDsho_3; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x180007c1a  mov     r9d, eax; char *
0x180007c1d  mov     edx, 18h; void *
0x180007c22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007c27  jmp     short loc_180007C2B
0x180007c29  xor     ebx, ebx
0x180007c2b  lea     rcx, [rsp+28h+arg_10]
0x180007c30  call    ??1?$com_ptr_t@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(void)
0x180007c35  jmp     short loc_180007C55
0x180007c37  mov     ebx, 8007000Eh
0x180007c3c  mov     edx, 15h; void *
0x180007c41  mov     rcx, [rsp+28h]; this
0x180007c46  lea     r8, aMultimediaDsho_3; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x180007c4d  mov     r9d, ebx; char *
0x180007c50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007c55  mov     eax, ebx
0x180007c57  mov     rbx, [rsp+28h+arg_0]
0x180007c5c  mov     rsi, [rsp+28h+arg_8]
0x180007c61  add     rsp, 20h
0x180007c65  pop     rdi
0x180007c66  retn
```
