# SString::ConvertToUnicode(void)

- ea: `0x14000b010`
- end: `0x14000b121`
- name: `?ConvertToUnicode@SString@@AEBAXXZ`
- size: `273`
- prototype: `void __fastcall(SString *__hidden this)`
- caller_count: `31`
- callee_count: `6`
- tags: ``

## callers

- `0x140001214`
- `0x140001504`
- `0x14000154c`
- `0x1400016f4`
- `0x140001950`
- `0x140001bac`
- `0x140002168`
- `0x140004694`
- `0x140006188`
- `0x1400068ec`
- `0x140006a5c`
- `0x140007100`
- `0x140007388`
- `0x140008548`
- `0x140009104`
- `0x140009a78`
- `0x14000a9bc`
- `0x14000aedc`
- `0x14000b37c`
- `0x14000b494`
- `0x14000b578`
- `0x14000b6e8`
- `0x14000b898`
- `0x14000c044`
- `0x14000c458`
- `0x140010ba8`
- `0x140010c68`
- `0x140010e48`
- `0x14001181c`
- `0x1400120d8`
- `0x14001281c`

## callees

- `0x140001100`
- `0x14000af84`
- `0x14000b010`
- `0x14000b268`
- `0x14000c39c`
- `0x140013200`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000b0f7`
- `KERNEL32!HeapFree` at `0x14000b0f7`
- `KERNEL32!GetProcessHeap` at `0x14000b0e2`
- `KERNEL32!GetProcessHeap` at `0x14000b0e2`

## pseudocode

```c
void __fastcall SString::ConvertToUnicode(SString *this)
{
  void *v2; // rbx
  HANDLE ProcessHeap; // rax
  int v4; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v5; // [rsp+24h] [rbp-DCh]
  LPVOID lpMem; // [rsp+30h] [rbp-D0h]
  __int16 v7; // [rsp+38h] [rbp-C8h] BYREF

  if ( (*((_BYTE *)this + 8) & 3) != 0 )
  {
    if ( (unsigned int)SString::IsRepresentation(this, 1) )
    {
      SString::ConvertASCIIToUnicode(this, this);
    }
    else
    {
      v5 = 512;
      lpMem = &v7;
      v4 = 2;
      v7 = 0;
      SString::ConvertToUnicode(this, (struct SString *)&v4);
      SBuffer::Set(this, (const struct SBuffer *)&v4);
      *((_DWORD *)this + 2) = BYTE4(v5) & 7 | *((_DWORD *)this + 2) & 0xFFFFFEF8;
      if ( (v5 & 0x800000000LL) != 0 )
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
  }
}

```

## disassembly

```asm
0x14000b010  mov     [rsp-8+arg_8], rbx
0x14000b015  mov     [rsp-8+arg_10], rdi
0x14000b01a  push    rbp
0x14000b01b  lea     rbp, [rsp-150h]
0x14000b023  sub     rsp, 250h
0x14000b02a  mov     rax, cs:__security_cookie
0x14000b031  xor     rax, rsp
0x14000b034  mov     [rbp+150h+var_10], rax
0x14000b03b  mov     rbx, rcx
0x14000b03e  test    byte ptr [rcx+8], 3
0x14000b042  jz      loc_14000B0FD
0x14000b048  mov     edx, 1
0x14000b04d  call    ?IsRepresentation@SString@@AEBAHW4Representation@1@@Z; SString::IsRepresentation(SString::Representation)
0x14000b052  xor     edi, edi
0x14000b054  test    eax, eax
0x14000b056  jz      short loc_14000B068
0x14000b058  mov     rdx, rbx; struct SString *
0x14000b05b  mov     rcx, rbx; this
0x14000b05e  call    ?ConvertASCIIToUnicode@SString@@AEBAXAEAV1@@Z; SString::ConvertASCIIToUnicode(SString &)
0x14000b063  jmp     loc_14000B0FD
0x14000b068  mov     [rsp+250h+var_230], rdi
0x14000b06d  mov     [rsp+250h+var_230+4], 200h
0x14000b076  mov     [rsp+250h+lpMem], rdi
0x14000b07b  lea     rax, [rsp+250h+var_218]
0x14000b080  mov     [rsp+250h+lpMem], rax
0x14000b085  mov     dword ptr [rsp+250h+var_230], 2
0x14000b08d  mov     rax, [rsp+250h+lpMem]
0x14000b092  mov     [rax], di
0x14000b095  lea     rdx, [rsp+250h+var_230]; struct SString *
0x14000b09a  mov     rcx, rbx; this
0x14000b09d  call    ?ConvertToUnicode@SString@@QEBAXAEAV1@@Z; SString::ConvertToUnicode(SString &)
0x14000b0a2  lea     rdx, [rsp+250h+var_230]; struct SBuffer *
0x14000b0a7  mov     rcx, rbx; this
0x14000b0aa  call    ?Set@SBuffer@@QEAAXAEBV1@@Z; SBuffer::Set(SBuffer const &)
0x14000b0af  mov     eax, [rsp+250h+var_228]
0x14000b0b3  and     eax, 7
0x14000b0b6  mov     ecx, [rbx+8]
0x14000b0b9  and     ecx, 0FFFFFFF8h
0x14000b0bc  or      ecx, eax
0x14000b0be  btr     ecx, 8
0x14000b0c2  mov     [rbx+8], ecx
0x14000b0c5  test    byte ptr [rsp+250h+var_228], 8
0x14000b0ca  jz      short loc_14000B0FD
0x14000b0cc  mov     rbx, [rsp+250h+lpMem]
0x14000b0d1  test    rbx, rbx
0x14000b0d4  jz      short loc_14000B0FD
0x14000b0d6  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x14000b0dd  test    rax, rax
0x14000b0e0  jnz     short loc_14000B0EF
0x14000b0e2  call    cs:__imp_GetProcessHeap
0x14000b0e8  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x14000b0ef  mov     r8, rbx; lpMem
0x14000b0f2  xor     edx, edx; dwFlags
0x14000b0f4  mov     rcx, rax; hHeap
0x14000b0f7  call    cs:__imp_HeapFree
0x14000b0fd  mov     rcx, [rbp+150h+var_10]
0x14000b104  xor     rcx, rsp; StackCookie
0x14000b107  call    __security_check_cookie
0x14000b10c  lea     r11, [rsp+250h+var_s0]
0x14000b114  mov     rbx, [r11+18h]
0x14000b118  mov     rdi, [r11+20h]
0x14000b11c  mov     rsp, r11
0x14000b11f  pop     rbp
0x14000b120  retn
```
