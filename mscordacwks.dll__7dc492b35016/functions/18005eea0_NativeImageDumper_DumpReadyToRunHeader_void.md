# NativeImageDumper::DumpReadyToRunHeader(void)

- ea: `0x18005eea0`
- end: `0x18005f0e5`
- name: `?DumpReadyToRunHeader@NativeImageDumper@@QEAAXXZ`
- size: `581`
- prototype: `void __fastcall(NativeImageDumper *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18005ecd4`

## callees

- `0x180022068`
- `0x18004240c`
- `0x180042724`
- `0x18005eea0`
- `0x18007344c`
- `0x1800f0d20`
- `0x180106100`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18005f0a3`
- `KERNEL32!HeapFree` at `0x18005f0a3`
- `KERNEL32!GetProcessHeap` at `0x18005f08e`
- `KERNEL32!GetProcessHeap` at `0x18005f08e`

## string_xrefs

- `0x18005ef0c`: `READYTORUN_HEADER`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall NativeImageDumper::DumpReadyToRunHeader(NativeImageDumper *this, __int64 a2)
{
  unsigned __int64 TargetAddrForHostAddr; // rax
  unsigned __int64 v4; // rax
  int v5; // eax
  void *v6; // rdi
  HANDLE ProcessHeap; // rax
  int v8; // [rsp+48h] [rbp-59h] BYREF
  __int64 v9; // [rsp+4Ch] [rbp-55h]
  LPVOID lpMem; // [rsp+58h] [rbp-49h]
  __int16 v11; // [rsp+60h] [rbp-41h] BYREF

  if ( (*((_DWORD *)this + 102) & 0x200) != 0 )
  {
    LOBYTE(a2) = 1;
    TargetAddrForHostAddr = DacGetTargetAddrForHostAddr(*(_QWORD *)this, a2);
    v4 = NativeImageDumper::DataPtrToDisplay(this, TargetAddrForHostAddr);
    (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64, __int64))(**((_QWORD **)this + 17) + 392LL))(
      *((_QWORD *)this + 17),
      "READYTORUN_HEADER",
      v4,
      16);
    v5 = *((_DWORD *)this + 102);
    if ( v5 )
    {
      (*(void (__fastcall **)(_QWORD, const char *, _QWORD, __int64, _DWORD))(**((_QWORD **)this + 17) + 344LL))(
        *((_QWORD *)this + 17),
        "Signature",
        0,
        4,
        **(_DWORD **)this);
      v5 = *((_DWORD *)this + 102);
      if ( v5 )
      {
        (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _DWORD))(**((_QWORD **)this + 17) + 344LL))(
          *((_QWORD *)this + 17),
          "MajorVersion",
          4,
          2,
          *(unsigned __int16 *)(*(_QWORD *)this + 4LL));
        v5 = *((_DWORD *)this + 102);
        if ( v5 )
        {
          (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _DWORD))(**((_QWORD **)this + 17) + 344LL))(
            *((_QWORD *)this + 17),
            "MinorVersion",
            6,
            2,
            *(unsigned __int16 *)(*(_QWORD *)this + 6LL));
          v5 = *((_DWORD *)this + 102);
        }
      }
    }
    if ( (v5 & 0x200) != 0 )
    {
      v9 = 128;
      lpMem = &v11;
      v8 = 2;
      v11 = 0;
      EnumFlagsToString(
        *(_DWORD *)(*(_QWORD *)this + 8LL),
        (const struct NativeImageDumper::EnumMnemonics *)&qword_180161DF0,
        1,
        L", ",
        (struct SString *)&v8);
      SString::ConvertToUnicode((SString *)&v8);
      (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 352LL))(
        *((_QWORD *)this + 17),
        "Flags",
        8);
      if ( (v9 & 0x800000000LL) != 0 )
      {
        v6 = lpMem;
        if ( lpMem )
        {
          ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
          if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
          {
            ProcessHeap = GetProcessHeap();
            `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
          }
          HeapFree(ProcessHeap, 0, v6);
        }
      }
    }
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
  }
}

```

## disassembly

```asm
0x18005eea0  mov     rax, rsp
0x18005eea3  mov     [rax+10h], rbx
0x18005eea7  mov     [rax+18h], rsi
0x18005eeab  mov     [rax+20h], rdi
0x18005eeaf  push    rbp
0x18005eeb0  lea     rbp, [rax-5Fh]
0x18005eeb4  sub     rsp, 0F0h
0x18005eebb  mov     rax, cs:__security_cookie
0x18005eec2  xor     rax, rsp
0x18005eec5  mov     [rbp+57h+var_10], rax
0x18005eec9  mov     rbx, rcx
0x18005eecc  mov     edi, 200h
0x18005eed1  test    [rcx+198h], edi
0x18005eed7  jz      loc_18005F0C0
0x18005eedd  mov     dl, 1
0x18005eedf  mov     rcx, [rcx]
0x18005eee2  call    DacGetTargetAddrForHostAddr
0x18005eee7  mov     rdx, rax; unsigned __int64
0x18005eeea  mov     rcx, rbx; this
0x18005eeed  call    ?DataPtrToDisplay@NativeImageDumper@@AEAA_K_K@Z; NativeImageDumper::DataPtrToDisplay(unsigned __int64)
0x18005eef2  mov     r8, rax
0x18005eef5  mov     rcx, [rbx+88h]
0x18005eefc  mov     rdx, [rcx]
0x18005eeff  mov     rax, [rdx+188h]
0x18005ef06  mov     r9d, 10h
0x18005ef0c  lea     rdx, aReadytorunHead; "READYTORUN_HEADER"
0x18005ef13  call    cs:__guard_dispatch_icall_fptr
0x18005ef19  mov     eax, [rbx+198h]
0x18005ef1f  xor     esi, esi
0x18005ef21  test    eax, eax
0x18005ef23  jz      loc_18005EFD7
0x18005ef29  mov     rcx, [rbx+88h]
0x18005ef30  mov     rax, [rcx]
0x18005ef33  mov     rdx, [rbx]
0x18005ef36  mov     edx, [rdx]
0x18005ef38  mov     dword ptr [rsp+0F0h+var_D0], edx
0x18005ef3c  lea     r9d, [rsi+4]
0x18005ef40  xor     r8d, r8d
0x18005ef43  lea     rdx, aSignature_0; "Signature"
0x18005ef4a  mov     rax, [rax+158h]
0x18005ef51  call    cs:__guard_dispatch_icall_fptr
0x18005ef57  mov     eax, [rbx+198h]
0x18005ef5d  test    eax, eax
0x18005ef5f  jz      short loc_18005EFD7
0x18005ef61  mov     rcx, [rbx+88h]
0x18005ef68  mov     rdx, [rcx]
0x18005ef6b  mov     rax, [rbx]
0x18005ef6e  movzx   r8d, word ptr [rax+4]
0x18005ef73  mov     rax, [rdx+158h]
0x18005ef7a  mov     dword ptr [rsp+0F0h+var_D0], r8d
0x18005ef7f  lea     r9d, [rsi+2]
0x18005ef83  lea     r8d, [rsi+4]
0x18005ef87  lea     rdx, aMajorversion; "MajorVersion"
0x18005ef8e  call    cs:__guard_dispatch_icall_fptr
0x18005ef94  mov     eax, [rbx+198h]
0x18005ef9a  test    eax, eax
0x18005ef9c  jz      short loc_18005EFD7
0x18005ef9e  mov     rcx, [rbx+88h]
0x18005efa5  mov     rdx, [rcx]
0x18005efa8  mov     rax, [rbx]
0x18005efab  movzx   r8d, word ptr [rax+6]
0x18005efb0  mov     rax, [rdx+158h]
0x18005efb7  mov     dword ptr [rsp+0F0h+var_D0], r8d
0x18005efbc  lea     r9d, [rsi+2]
0x18005efc0  lea     r8d, [rsi+6]
0x18005efc4  lea     rdx, aMinorversion; "MinorVersion"
0x18005efcb  call    cs:__guard_dispatch_icall_fptr
0x18005efd1  mov     eax, [rbx+198h]
0x18005efd7  test    edi, eax
0x18005efd9  jz      loc_18005F0A9
0x18005efdf  mov     [rbp+57h+var_B0], rsi
0x18005efe3  mov     [rbp+57h+var_B0+4], 80h
0x18005efeb  mov     [rbp+57h+lpMem], rsi
0x18005efef  lea     rax, [rbp+57h+var_98]
0x18005eff3  mov     [rbp+57h+lpMem], rax
0x18005eff7  mov     dword ptr [rbp+57h+var_B0], 2
0x18005effe  mov     rax, [rbp+57h+lpMem]
0x18005f002  mov     [rax], si
0x18005f005  mov     rax, [rbx]
0x18005f008  lea     rcx, [rbp+57h+var_B0]
0x18005f00c  mov     [rsp+0F0h+var_D0], rcx; struct SString *
0x18005f011  lea     r9, asc_180137070; ", "
0x18005f018  mov     r8d, 1; int
0x18005f01e  lea     rdx, qword_180161DF0; struct NativeImageDumper::EnumMnemonics *
0x18005f025  mov     ecx, [rax+8]; unsigned int
0x18005f028  call    ?EnumFlagsToString@@YAXKPEBUEnumMnemonics@NativeImageDumper@@HPEBGAEAVSString@@@Z; EnumFlagsToString(ulong,NativeImageDumper::EnumMnemonics const *,int,ushort const *,SString &)
0x18005f02d  lea     rcx, [rbp+57h+var_B0]; this
0x18005f031  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18005f036  mov     rcx, [rbx+88h]
0x18005f03d  mov     rax, [rcx]
0x18005f040  mov     r8, [rbx]
0x18005f043  mov     rdx, [rbp+57h+lpMem]
0x18005f047  mov     [rsp+0F0h+var_C8], rdx
0x18005f04c  mov     edx, [r8+8]
0x18005f050  mov     dword ptr [rsp+0F0h+var_D0], edx
0x18005f054  mov     r9d, 4
0x18005f05a  lea     r8d, [r9+4]
0x18005f05e  lea     rdx, aFlags_0; "Flags"
0x18005f065  mov     rax, [rax+160h]
0x18005f06c  call    cs:__guard_dispatch_icall_fptr
0x18005f072  nop
0x18005f073  test    [rbp+57h+var_A8], 8
0x18005f077  jz      short loc_18005F0A9
0x18005f079  mov     rdi, [rbp+57h+lpMem]
0x18005f07d  test    rdi, rdi
0x18005f080  jz      short loc_18005F0A9
0x18005f082  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18005f089  test    rax, rax
0x18005f08c  jnz     short loc_18005F09B
0x18005f08e  call    cs:__imp_GetProcessHeap
0x18005f094  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18005f09b  mov     r8, rdi; lpMem
0x18005f09e  xor     edx, edx; dwFlags
0x18005f0a0  mov     rcx, rax; hHeap
0x18005f0a3  call    cs:__imp_HeapFree
0x18005f0a9  mov     rcx, [rbx+88h]
0x18005f0b0  mov     rax, [rcx]
0x18005f0b3  mov     rax, [rax+1A0h]
0x18005f0ba  call    cs:__guard_dispatch_icall_fptr
0x18005f0c0  mov     rcx, [rbp+57h+var_10]
0x18005f0c4  xor     rcx, rsp; StackCookie
0x18005f0c7  call    __security_check_cookie
0x18005f0cc  lea     r11, [rsp+0F0h+var_s0]
0x18005f0d4  mov     rbx, [r11+18h]
0x18005f0d8  mov     rsi, [r11+20h]
0x18005f0dc  mov     rdi, [r11+28h]
0x18005f0e0  mov     rsp, r11
0x18005f0e3  pop     rbp
0x18005f0e4  retn
```
