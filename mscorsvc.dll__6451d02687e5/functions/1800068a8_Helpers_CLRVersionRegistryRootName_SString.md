# Helpers::CLRVersionRegistryRootName(SString &)

- ea: `0x1800068a8`
- end: `0x180006a10`
- name: `?CLRVersionRegistryRootName@Helpers@@SAXAEAVSString@@@Z`
- size: `360`
- prototype: `void __fastcall(struct SString *this)`
- caller_count: `10`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800036b0`
- `0x180003874`
- `0x180003a54`
- `0x180006328`
- `0x180016794`
- `0x180016920`
- `0x180016a9c`
- `0x180016ca8`
- `0x1800198dc`
- `0x18001b57c`

## callees

- `0x180001de0`
- `0x180001e8c`
- `0x180002468`
- `0x1800064a8`
- `0x180006680`
- `0x1800068a8`
- `0x180030568`
- `0x180030ab8`
- `0x18003dc30`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800069d5`
- `KERNEL32!HeapFree` at `0x1800069d5`
- `KERNEL32!GetProcessHeap` at `0x1800069c0`
- `KERNEL32!GetProcessHeap` at `0x1800069c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
void __fastcall Helpers::CLRVersionRegistryRootName(struct SString *this)
{
  void *v2; // rbx
  HANDLE ProcessHeap; // rax
  _DWORD v4[2]; // [rsp+20h] [rbp-E0h] BYREF
  int v5; // [rsp+28h] [rbp-D8h]
  void *v6; // [rsp+30h] [rbp-D0h]
  int v7; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v8; // [rsp+44h] [rbp-BCh]
  LPVOID lpMem; // [rsp+50h] [rbp-B0h]
  __int16 v10; // [rsp+58h] [rbp-A8h] BYREF

  v4[0] = 2;
  v4[1] = 2;
  v5 = 16;
  v6 = (void *)&SString::s_EmptyBuffer;
  SString::Set((SString *)v4, L"SOFTWARE\\Microsoft\\.NetFramework");
  SBuffer::Set(this, (const struct SBuffer *)v4);
  *((_DWORD *)this + 2) = v5 & 7 | *((_DWORD *)this + 2) & 0xFFFFFEF8;
  if ( (v5 & 8) != 0 )
    operator delete(v6);
  if ( (unsigned int)Helpers::IsUsingPrivateStore() )
  {
    v8 = 512;
    lpMem = &v10;
    v7 = 2;
    v10 = 0;
    Helpers::GetVersionDirectoryFromCurrentModulePath((struct SString *)&v7);
    SString::Append(this, L"\\");
    SString::Append(this, (const struct SString *)&v7);
    if ( (v8 & 0x800000000LL) != 0 )
    {
      v2 = lpMem;
      if ( lpMem )
      {
        ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          ProcessHeap = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
        }
        HeapFree(ProcessHeap, 0, v2);
      }
    }
  }
  else
  {
    SString::Append(this, L"\\v2.0.50727");
  }
}

```

## disassembly

```asm
0x1800068a8  mov     [rsp-8+arg_8], rbx
0x1800068ad  mov     [rsp-8+arg_10], rdi
0x1800068b2  push    rbp
0x1800068b3  lea     rbp, [rsp-170h]
0x1800068bb  sub     rsp, 270h
0x1800068c2  mov     rax, cs:__security_cookie
0x1800068c9  xor     rax, rsp
0x1800068cc  mov     [rbp+170h+var_10], rax
0x1800068d3  mov     rbx, rcx
0x1800068d6  mov     [rsp+270h+var_250], 2
0x1800068de  mov     [rsp+270h+var_24C], 2
0x1800068e6  mov     [rsp+270h+var_248], 10h
0x1800068ee  lea     rax, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x1800068f5  mov     [rsp+270h+var_240], rax
0x1800068fa  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\.NetFramework"
0x180006901  lea     rcx, [rsp+270h+var_250]; this
0x180006906  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x18000690b  nop
0x18000690c  lea     rdx, [rsp+270h+var_250]; struct SBuffer *
0x180006911  mov     rcx, rbx; this
0x180006914  call    ?Set@SBuffer@@QEAAXAEBV1@@Z; SBuffer::Set(SBuffer const &)
0x180006919  mov     ecx, [rsp+270h+var_248]
0x18000691d  and     ecx, 7
0x180006920  mov     eax, [rbx+8]
0x180006923  and     eax, 0FFFFFFF8h
0x180006926  or      eax, ecx
0x180006928  btr     eax, 8
0x18000692c  mov     [rbx+8], eax
0x18000692f  test    byte ptr [rsp+270h+var_248], 8
0x180006934  jz      short loc_180006940
0x180006936  mov     rcx, [rsp+270h+var_240]; lpMem
0x18000693b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006940  call    ?IsUsingPrivateStore@Helpers@@SAHXZ; Helpers::IsUsingPrivateStore(void)
0x180006945  xor     edi, edi
0x180006947  test    eax, eax
0x180006949  jz      loc_1800069DD
0x18000694f  mov     [rsp+270h+var_230], rdi
0x180006954  mov     [rsp+270h+var_230+4], 200h
0x18000695d  mov     [rsp+270h+lpMem], rdi
0x180006962  lea     rax, [rsp+270h+var_218]
0x180006967  mov     [rsp+270h+lpMem], rax
0x18000696c  mov     dword ptr [rsp+270h+var_230], 2
0x180006974  mov     rax, [rsp+270h+lpMem]
0x180006979  mov     [rax], di
0x18000697c  lea     rcx, [rsp+270h+var_230]; this
0x180006981  call    ?GetVersionDirectoryFromCurrentModulePath@Helpers@@SAXAEAVSString@@@Z; Helpers::GetVersionDirectoryFromCurrentModulePath(SString &)
0x180006986  lea     rdx, asc_180049544; "\\"
0x18000698d  mov     rcx, rbx; this
0x180006990  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x180006995  lea     rdx, [rsp+270h+var_230]; struct SString *
0x18000699a  mov     rcx, rbx; this
0x18000699d  call    ?Append@SString@@QEAAXAEBV1@@Z; SString::Append(SString const &)
0x1800069a2  nop
0x1800069a3  test    [rsp+270h+var_228], 8
0x1800069a8  jz      short loc_1800069EC
0x1800069aa  mov     rbx, [rsp+270h+lpMem]
0x1800069af  test    rbx, rbx
0x1800069b2  jz      short loc_1800069EC
0x1800069b4  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800069bb  test    rax, rax
0x1800069be  jnz     short loc_1800069CD
0x1800069c0  call    cs:__imp_GetProcessHeap
0x1800069c6  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800069cd  mov     r8, rbx; lpMem
0x1800069d0  xor     edx, edx; dwFlags
0x1800069d2  mov     rcx, rax; hHeap
0x1800069d5  call    cs:__imp_HeapFree
0x1800069db  jmp     short loc_1800069EC
0x1800069dd  lea     rdx, aV2050727_0; "\\v2.0.50727"
0x1800069e4  mov     rcx, rbx; this
0x1800069e7  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x1800069ec  mov     rcx, [rbp+170h+var_10]
0x1800069f3  xor     rcx, rsp; StackCookie
0x1800069f6  call    __security_check_cookie
0x1800069fb  lea     r11, [rsp+270h+var_s0]
0x180006a03  mov     rbx, [r11+18h]
0x180006a07  mov     rdi, [r11+20h]
0x180006a0b  mov     rsp, r11
0x180006a0e  pop     rbp
0x180006a0f  retn
```
