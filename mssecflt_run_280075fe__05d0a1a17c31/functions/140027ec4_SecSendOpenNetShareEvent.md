# SecSendOpenNetShareEvent

- ea: `0x140027ec4`
- end: `0x1400280f6`
- name: `SecSendOpenNetShareEvent`
- size: `562`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x1400247b8`

## callees

- `0x140005230`
- `0x140005f34`
- `0x1400061dc`
- `0x140006684`
- `0x140006754`
- `0x140006b6c`
- `0x140006d3c`
- `0x1400102ff`
- `0x140010347`
- `0x1400103e3`
- `0x140011650`
- `0x140027ec4`
- `0x140028b20`
- `0x140029658`

## import_xrefs

- `ntoskrnl!PsGetThreadId` at `0x140027ffb`
- `ntoskrnl!PsGetThreadId` at `0x140027ffb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400280a1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400280a1`

## pseudocode

```c
void __fastcall SecSendOpenNetShareEvent(PFLT_CALLBACK_DATA CallbackData, __int64 a2, int a3, _QWORD *a4)
{
  __int64 RequestorProcess; // rax
  struct _KTHREAD *Thread; // rbx
  char ThreadId; // al
  int Next; // r14d
  void *Sid; // r11
  int v13; // edi
  struct _SLIST_ENTRY *v14; // r9
  __int64 v15; // r8
  __int64 v16; // rcx
  PSLIST_ENTRY ListEntry; // [rsp+60h] [rbp-39h] BYREF
  PVOID P; // [rsp+68h] [rbp-31h] BYREF
  PFLT_CONTEXT Context; // [rsp+70h] [rbp-29h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+78h] [rbp-21h]
  wchar_t *v21[2]; // [rsp+80h] [rbp-19h] BYREF
  wchar_t *v22[2]; // [rsp+90h] [rbp-9h] BYREF
  wchar_t *Str[2]; // [rsp+A0h] [rbp+7h] BYREF
  _BYTE v24[4]; // [rsp+B0h] [rbp+17h] BYREF
  __int16 v25; // [rsp+B4h] [rbp+1Bh] BYREF

  ListEntry = 0;
  P = 0;
  v24[0] = 0;
  Context = 0;
  FileNameInformation = 0;
  *(_OWORD *)Str = 0;
  v25 = 0;
  *(_OWORD *)v21 = 0;
  *(_OWORD *)v22 = 0;
  if ( (xmmword_14001B740 & 0x10000000) != 0 )
  {
    if ( a3 == 1 )
    {
      SecUnicodeToNullTerminatedUnicode(*a4, v21);
      SecGetIpAddressFromSocketAddress(a4[1], v22, &v25);
    }
    RequestorProcess = SecFltGetRequestorProcess(CallbackData);
    if ( (int)SecGetProcessContextByObject(RequestorProcess, &ListEntry) >= 0
      && FltGetInstanceContext_0(*(PFLT_INSTANCE *)(a2 + 24), &Context) >= 0 )
    {
      _mm_lfence();
      if ( (int)SecQueryFileName(CallbackData) >= 0 )
      {
        _mm_lfence();
        Thread = CallbackData->Thread;
        if ( !Thread )
          Thread = KeGetCurrentThread();
        if ( (int)SecGetEffectiveTokenUser(Thread, (__int64)ListEntry, &P, v24, 0) >= 0
          && (int)SecUnicodeToNullTerminatedUnicode(&FileNameInformation->Name, Str) >= 0 )
        {
          _mm_lfence();
          ThreadId = (unsigned __int8)PsGetThreadId(Thread);
          Next = (int)ListEntry[2].Next;
          Sid = *(void **)P;
          v13 = *((_DWORD *)&ListEntry[38].Next + 2);
          v14 = ListEntry[3].Next;
          v15 = *((_QWORD *)&ListEntry[2].Next + 1);
          v16 = _InterlockedIncrement64((volatile signed __int64 *)SecData + 42);
          EventWriteOpenNetShare(v16, Next, v15, (__int64)v14, ThreadId, Sid, v13, Str[1], v21[1], v22[1], a3);
        }
      }
    }
  }
  SecFreeNullTerminatedUnicode(v21);
  SecFreeNullTerminatedUnicode(v22);
  SecFreeNullTerminatedUnicode(Str);
  if ( P && v24[0] )
    ExFreePoolWithTag(P, 0);
  if ( Context )
    FltReleaseContext_0(Context);
  if ( ListEntry )
    SecReleaseProcessContext(ListEntry);
  if ( FileNameInformation )
    FltReleaseFileNameInformation_0(FileNameInformation);
}

```

## disassembly

```asm
0x140027ec4  push    rbp
0x140027ec6  push    rbx
0x140027ec7  push    rsi
0x140027ec8  push    rdi
0x140027ec9  push    r12
0x140027ecb  push    r14
0x140027ecd  push    r15
0x140027ecf  lea     rbp, [rsp-27h]
0x140027ed4  sub     rsp, 0C0h
0x140027edb  mov     rax, cs:__security_cookie
0x140027ee2  xor     rax, rsp
0x140027ee5  mov     [rbp+57h+var_38], rax
0x140027ee9  xor     r12d, r12d
0x140027eec  xorps   xmm0, xmm0
0x140027eef  test    qword ptr cs:xmmword_14001B740, 10000000h
0x140027efa  xorps   xmm1, xmm1
0x140027efd  mov     rdi, r9
0x140027f00  mov     [rbp+57h+ListEntry], r12
0x140027f04  mov     r15d, r8d
0x140027f07  mov     [rbp+57h+P], r12
0x140027f0b  mov     rsi, rdx
0x140027f0e  mov     [rbp+57h+var_40], r12b
0x140027f12  mov     rbx, rcx
0x140027f15  mov     [rbp+57h+Context], r12
0x140027f19  mov     [rbp+57h+FileNameInformation], r12
0x140027f1d  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x140027f21  mov     [rbp+57h+var_3C], r12w
0x140027f26  movups  xmmword ptr [rbp+57h+var_70], xmm1
0x140027f2a  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x140027f2e  jz      loc_140028075
0x140027f34  cmp     r8d, 1
0x140027f38  jnz     short loc_140027F57
0x140027f3a  mov     rcx, [r9]
0x140027f3d  lea     rdx, [rbp+57h+var_70]
0x140027f41  call    SecUnicodeToNullTerminatedUnicode
0x140027f46  mov     rcx, [rdi+8]
0x140027f4a  lea     r8, [rbp+57h+var_3C]
0x140027f4e  lea     rdx, [rbp+57h+var_60]
0x140027f52  call    SecGetIpAddressFromSocketAddress
0x140027f57  mov     rcx, rbx
0x140027f5a  call    SecFltGetRequestorProcess
0x140027f5f  mov     rcx, rax
0x140027f62  lea     rdx, [rbp+57h+ListEntry]
0x140027f66  call    SecGetProcessContextByObject
0x140027f6b  test    eax, eax
0x140027f6d  js      loc_140028075
0x140027f73  mov     rcx, [rsi+18h]; Instance
0x140027f77  lea     rdx, [rbp+57h+Context]; Context
0x140027f7b  call    FltGetInstanceContext_0
0x140027f80  test    eax, eax
0x140027f82  js      loc_140028075
0x140027f88  lfence
0x140027f8b  mov     rdx, [rbp+57h+Context]
0x140027f8f  lea     r8, [rbp+57h+FileNameInformation]
0x140027f93  mov     rcx, rbx; CallbackData
0x140027f96  mov     edx, [rdx+2Ch]
0x140027f99  call    SecQueryFileName
0x140027f9e  test    eax, eax
0x140027fa0  js      loc_140028075
0x140027fa6  lfence
0x140027fa9  mov     rbx, [rbx+8]
0x140027fad  test    rbx, rbx
0x140027fb0  jnz     short loc_140027FBB
0x140027fb2  mov     rbx, gs:188h
0x140027fbb  mov     rdx, [rbp+57h+ListEntry]
0x140027fbf  lea     r9, [rbp+57h+var_40]
0x140027fc3  lea     r8, [rbp+57h+P]
0x140027fc7  mov     qword ptr [rsp+0F0h+var_D0], r12; __int64
0x140027fcc  mov     rcx, rbx; Thread
0x140027fcf  call    SecGetEffectiveTokenUser
0x140027fd4  test    eax, eax
0x140027fd6  js      loc_140028075
0x140027fdc  mov     rcx, [rbp+57h+FileNameInformation]
0x140027fe0  lea     rdx, [rbp+57h+var_50]
0x140027fe4  add     rcx, 8
0x140027fe8  call    SecUnicodeToNullTerminatedUnicode
0x140027fed  test    eax, eax
0x140027fef  js      loc_140028075
0x140027ff5  lfence
0x140027ff8  mov     rcx, rbx; Thread
0x140027ffb  call    cs:__imp_PsGetThreadId
0x140028002  nop     dword ptr [rax+rax+00h]
0x140028007  mov     rdx, [rbp+57h+ListEntry]
0x14002800b  mov     ebx, 1
0x140028010  mov     rcx, [rbp+57h+P]
0x140028014  mov     rsi, rax
0x140028017  mov     r14d, [rdx+20h]
0x14002801b  mov     r11, [rcx]
0x14002801e  mov     rcx, cs:SecData
0x140028025  mov     edi, [rdx+268h]
0x14002802b  mov     r9, [rdx+30h]; int
0x14002802f  mov     r8, [rdx+28h]; int
0x140028033  lock xadd [rcx+150h], rbx
0x14002803c  mov     rax, [rbp+57h+var_70+8]
0x140028040  lea     rcx, [rbx+1]; int
0x140028044  mov     r10, [rbp+57h+var_60+8]
0x140028048  mov     edx, r14d; int
0x14002804b  mov     dword ptr [rsp+0F0h+var_A0], r15d; char
0x140028050  mov     [rsp+0F0h+var_A8], r10; wchar_t *
0x140028055  mov     [rsp+0F0h+var_B0], rax; wchar_t *
0x14002805a  mov     rax, [rbp+57h+var_50+8]
0x14002805e  mov     [rsp+0F0h+Str], rax; Str
0x140028063  mov     dword ptr [rsp+0F0h+var_C0], edi; char
0x140028067  mov     [rsp+0F0h+Sid], r11; Sid
0x14002806c  mov     dword ptr [rsp+0F0h+var_D0], esi; char
0x140028070  call    EventWriteOpenNetShare
0x140028075  lea     rcx, [rbp+57h+var_70]
0x140028079  call    SecFreeNullTerminatedUnicode
0x14002807e  lea     rcx, [rbp+57h+var_60]
0x140028082  call    SecFreeNullTerminatedUnicode
0x140028087  lea     rcx, [rbp+57h+var_50]
0x14002808b  call    SecFreeNullTerminatedUnicode
0x140028090  mov     rcx, [rbp+57h+P]; P
0x140028094  test    rcx, rcx
0x140028097  jz      short loc_1400280AD
0x140028099  cmp     [rbp+57h+var_40], r12b
0x14002809d  jz      short loc_1400280AD
0x14002809f  xor     edx, edx; Tag
0x1400280a1  call    cs:__imp_ExFreePoolWithTag
0x1400280a8  nop     dword ptr [rax+rax+00h]
0x1400280ad  mov     rcx, [rbp+57h+Context]; Context
0x1400280b1  test    rcx, rcx
0x1400280b4  jz      short loc_1400280BB
0x1400280b6  call    FltReleaseContext_0
0x1400280bb  mov     rcx, [rbp+57h+ListEntry]; ListEntry
0x1400280bf  test    rcx, rcx
0x1400280c2  jz      short loc_1400280C9
0x1400280c4  call    SecReleaseProcessContext
0x1400280c9  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x1400280cd  test    rcx, rcx
0x1400280d0  jz      short loc_1400280D7
0x1400280d2  call    FltReleaseFileNameInformation_0
0x1400280d7  mov     rcx, [rbp+57h+var_38]
0x1400280db  xor     rcx, rsp; StackCookie
0x1400280de  call    __security_check_cookie
0x1400280e3  add     rsp, 0C0h
0x1400280ea  pop     r15
0x1400280ec  pop     r14
0x1400280ee  pop     r12
0x1400280f0  pop     rdi
0x1400280f1  pop     rsi
0x1400280f2  pop     rbx
0x1400280f3  pop     rbp
0x1400280f4  retn
```
