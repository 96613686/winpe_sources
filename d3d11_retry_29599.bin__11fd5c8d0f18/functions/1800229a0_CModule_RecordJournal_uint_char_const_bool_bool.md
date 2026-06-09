# CModule::RecordJournal(uint,char const *,bool,bool)

- ea: `0x1800229a0`
- end: `0x180022b81`
- name: `?RecordJournal@CModule@@QEAAXIPEBD_N1@Z`
- size: `481`
- prototype: `void(CModule *__hidden this, unsigned int, const char *, bool, bool)`
- caller_count: `132`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800214a0`
- `0x1800215e0`
- `0x180021700`
- `0x180021b10`
- `0x180021b90`
- `0x180021cb0`
- `0x180022460`
- `0x180022bf0`
- `0x180022c34`
- `0x180022cc0`
- `0x180022fe4`
- `0x180023124`
- `0x1800231ec`
- `0x1800232b4`
- `0x180024944`
- `0x180025fac`
- `0x1800337e0`
- `0x1800341a0`
- `0x1800346b0`
- `0x1800430ec`
- `0x1800475a0`
- `0x180047a80`
- `0x180048b40`
- `0x1800494d4`
- `0x18004ab48`
- `0x18004b5b0`
- `0x180059140`
- `0x1800591d8`
- `0x18005996c`
- `0x180059aec`
- `0x180059bcc`
- `0x18005a904`
- `0x18005aee8`
- `0x18005b0bc`
- `0x18005b2fc`
- `0x18005b340`
- `0x18005d1b0`
- `0x18005e200`
- `0x18005e38c`
- `0x180067280`
- `0x18006a958`
- `0x18006bb14`
- `0x18006d1e0`
- `0x18006d948`
- `0x18006dd10`
- `0x18006efd8`
- `0x18006f6cc`
- `0x18006f8e8`
- `0x18006f930`
- `0x18006fa4c`

## callees

- `0x1800229a0`
- `0x1800974b0`
- `0x1800a9d20`
- `0x1800aa9a8`

## import_xrefs

- `ntdll!RtlCaptureStackBackTrace` at `0x180022aa4`
- `ntdll!RtlCaptureStackBackTrace` at `0x180022aa4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800229f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022aec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800229f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022aec`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180022a01`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180022a01`

## pseudocode

```c
void __fastcall CModule::RecordJournal(CModule *this, int a2, char *a3, __int64 a4, bool a5)
{
  __int64 v8; // r14
  __int64 v9; // rdi
  __int64 v10; // rcx
  char *v11; // rdx
  __int64 v12; // r9
  char *v13; // r8
  char *v14; // rax
  USHORT v15; // ax
  int v16; // ecx
  unsigned int v17; // r10d
  __int64 v18; // r8
  unsigned __int64 v19; // r9
  PVOID v20; // rdx
  DWORD CurrentThreadId; // eax
  int v22; // edx
  int v23; // ecx
  unsigned __int64 v24; // r11
  PVOID v25; // rax
  PVOID BackTrace[50]; // [rsp+30h] [rbp-1D8h] BYREF

  v8 = ((unsigned __int8)_InterlockedExchangeAdd((volatile signed __int32 *)&JournalCounter, 0xFFFFFFFF) - 1) & 0x3F;
  v9 = 120 * v8;
  *((_DWORD *)&Journal + 30 * v8) = a2;
  *(_DWORD *)((char *)&Journal + v9 + 4) = GetCurrentThreadId();
  *(_DWORD *)((char *)&Journal + v9 + 8) = GetTickCount();
  *(_OWORD *)((char *)&Journal + v9 + 16) = 0;
  *(_QWORD *)((char *)&Journal + v9 + 32) = 0;
  *(_QWORD *)((char *)&Journal + v9 + 40) = 0;
  v10 = 2147483646;
  *(_QWORD *)((char *)&Journal + v9 + 48) = 0;
  v11 = a3;
  v12 = 64;
  v13 = (char *)&unk_1802295C8 + 120 * v8;
  do
  {
    if ( !v10 )
      break;
    if ( !*v11 )
      break;
    *v13++ = *v11++;
    --v10;
    --v12;
  }
  while ( v12 );
  v14 = v13 - 1;
  if ( v12 )
    v14 = v13;
  *v14 = 0;
  memset_0(BackTrace, 0, sizeof(BackTrace));
  v15 = 0;
  if ( a5 )
  {
    v15 = RtlCaptureStackBackTrace(1u, 0x32u, BackTrace, 0);
    if ( v15 >= 3u )
    {
      *(PVOID *)((char *)&Journal + v9 + 16) = BackTrace[0];
      *(PVOID *)((char *)&Journal + v9 + 24) = BackTrace[1];
      *(PVOID *)((char *)&Journal + v9 + 32) = BackTrace[2];
    }
  }
  v16 = 0;
  v17 = v15;
  do
  {
    v18 = (unsigned int)(v16 + 1);
    if ( (unsigned int)v18 >= v17 )
      break;
    v19 = *((_QWORD *)this + 12);
    v20 = BackTrace[v16];
    if ( (unsigned __int64)v20 >= v19 )
    {
      v24 = *((_QWORD *)this + 13);
      if ( (unsigned __int64)v20 <= v24 )
      {
        v25 = BackTrace[v18];
        if ( (unsigned __int64)v25 < v19 || (unsigned __int64)v25 > v24 )
        {
          *((_QWORD *)&Journal + 15 * v8 + 5) = v20;
          ++v16;
          *(_QWORD *)((char *)&Journal + v9 + 48) = v25;
        }
      }
    }
    ++v16;
  }
  while ( (unsigned int)(v16 + 1) < 0x32 );
  if ( (byte_180229581 & 4) != 0 )
  {
    CurrentThreadId = GetCurrentThreadId();
    McTemplateU0qdqs_EtwEventWriteTransfer(v23, v22, v8, a2, CurrentThreadId, a3);
  }
}

```

## disassembly

```asm
0x1800229a0  mov     [rsp+arg_0], rbx
0x1800229a5  push    rbp
0x1800229a6  push    rsi
0x1800229a7  push    rdi
0x1800229a8  push    r12
0x1800229aa  push    r13
0x1800229ac  push    r14
0x1800229ae  push    r15
0x1800229b0  sub     rsp, 1D0h
0x1800229b7  mov     rax, cs:__security_cookie
0x1800229be  xor     rax, rsp
0x1800229c1  mov     [rsp+208h+var_48], rax
0x1800229c9  mov     rbp, r8
0x1800229cc  mov     esi, edx
0x1800229ce  mov     rbx, rcx
0x1800229d1  mov     r14d, 0FFFFFFFFh
0x1800229d7  lock xadd cs:?JournalCounter@@3IC, r14d; uint volatile JournalCounter
0x1800229e0  dec     r14d
0x1800229e3  lea     r12, ?Journal@@3PAUSJournalEntry@@A; SJournalEntry near * Journal
0x1800229ea  and     r14d, 3Fh
0x1800229ee  imul    rdi, r14, 78h ; 'x'
0x1800229f2  mov     [rdi+r12], edx
0x1800229f6  call    cs:__imp_GetCurrentThreadId
0x1800229fc  mov     [rdi+r12+4], eax
0x180022a01  call    cs:__imp_GetTickCount
0x180022a07  mov     [rdi+r12+8], eax
0x180022a0c  xor     r13d, r13d
0x180022a0f  xor     eax, eax
0x180022a11  lea     r8, ?Journal@@3PAUSJournalEntry@@A; SJournalEntry near * Journal
0x180022a18  xorps   xmm0, xmm0
0x180022a1b  lea     r15, [rdi+r12]
0x180022a1f  movups  xmmword ptr [rdi+r12+10h], xmm0
0x180022a25  mov     [rdi+r12+20h], rax
0x180022a2a  add     r8, 38h ; '8'
0x180022a2e  mov     [r15+28h], r13
0x180022a32  mov     ecx, 7FFFFFFEh
0x180022a37  mov     [r12+rdi+30h], r13
0x180022a3c  mov     rdx, rbp
0x180022a3f  mov     r9d, 40h ; '@'
0x180022a45  add     r8, rdi
0x180022a48  test    rcx, rcx
0x180022a4b  jz      short loc_180022A66
0x180022a4d  movzx   eax, byte ptr [rdx]
0x180022a50  test    al, al
0x180022a52  jz      short loc_180022A66
0x180022a54  mov     [r8], al
0x180022a57  inc     rdx
0x180022a5a  inc     r8
0x180022a5d  dec     rcx
0x180022a60  sub     r9, 1
0x180022a64  jnz     short loc_180022A48
0x180022a66  lea     rax, [r8-1]
0x180022a6a  test    r9, r9
0x180022a6d  lea     rcx, [rsp+208h+BackTrace]; void *
0x180022a72  cmovnz  rax, r8
0x180022a76  xor     edx, edx; Val
0x180022a78  mov     r8d, 190h; Size
0x180022a7e  mov     [rax], r13b
0x180022a81  call    memset_0
0x180022a86  mov     eax, r13d
0x180022a89  cmp     [rsp+208h+arg_20], al
0x180022a90  jz      short loc_180022AB4
0x180022a92  xor     r9d, r9d; BackTraceHash
0x180022a95  lea     r8, [rsp+208h+BackTrace]; BackTrace
0x180022a9a  mov     edx, 32h ; '2'; FramesToCapture
0x180022a9f  mov     ecx, 1; FramesToSkip
0x180022aa4  call    cs:__imp_RtlCaptureStackBackTrace
0x180022aaa  cmp     ax, 3
0x180022aae  jnb     loc_180022B57
0x180022ab4  mov     ecx, r13d
0x180022ab7  movzx   r10d, ax
0x180022abb  nop     dword ptr [rax+rax+00h]
0x180022ac0  lea     r8d, [rcx+1]
0x180022ac4  cmp     r8d, r10d
0x180022ac7  jnb     short loc_180022AE3
0x180022ac9  mov     r9, [rbx+60h]
0x180022acd  mov     eax, ecx
0x180022acf  mov     rdx, [rsp+rax*8+208h+BackTrace]
0x180022ad4  cmp     rdx, r9
0x180022ad7  jnb     short loc_180022B31
0x180022ad9  inc     ecx
0x180022adb  lea     eax, [rcx+1]
0x180022ade  cmp     eax, 32h ; '2'
0x180022ae1  jb      short loc_180022AC0
0x180022ae3  test    cs:byte_180229581, 4
0x180022aea  jz      short loc_180022B06
0x180022aec  call    cs:__imp_GetCurrentThreadId
0x180022af2  mov     r9d, esi; int
0x180022af5  mov     [rsp+208h+Str], rbp; Str
0x180022afa  mov     r8d, r14d; int
0x180022afd  mov     [rsp+208h+var_1E8], eax; int
0x180022b01  call    McTemplateU0qdqs_EtwEventWriteTransfer
0x180022b06  mov     rcx, [rsp+208h+var_48]
0x180022b0e  xor     rcx, rsp; StackCookie
0x180022b11  call    __security_check_cookie
0x180022b16  mov     rbx, [rsp+208h+arg_0]
0x180022b1e  add     rsp, 1D0h
0x180022b25  pop     r15
0x180022b27  pop     r14
0x180022b29  pop     r13
0x180022b2b  pop     r12
0x180022b2d  pop     rdi
0x180022b2e  pop     rsi
0x180022b2f  pop     rbp
0x180022b30  retn
0x180022b31  mov     r11, [rbx+68h]
0x180022b35  cmp     rdx, r11
0x180022b38  ja      short loc_180022AD9
0x180022b3a  mov     rax, [rsp+r8*8+208h+BackTrace]
0x180022b3f  cmp     rax, r9
0x180022b42  jb      short loc_180022B49
0x180022b44  cmp     rax, r11
0x180022b47  jbe     short loc_180022AD9
0x180022b49  mov     [r15+28h], rdx
0x180022b4d  mov     ecx, r8d
0x180022b50  mov     [r12+rdi+30h], rax
0x180022b55  jmp     short loc_180022AD9
0x180022b57  mov     rcx, [rsp+208h+BackTrace]
0x180022b5c  lea     rdx, ?Journal@@3PAUSJournalEntry@@A; SJournalEntry near * Journal
0x180022b63  mov     [rdi+rdx+10h], rcx
0x180022b68  mov     rcx, [rsp+208h+var_1D0]
0x180022b6d  mov     [rdi+rdx+18h], rcx
0x180022b72  mov     rcx, [rsp+208h+var_1C8]
0x180022b77  mov     [rdi+rdx+20h], rcx
0x180022b7c  jmp     loc_180022AB4
```
