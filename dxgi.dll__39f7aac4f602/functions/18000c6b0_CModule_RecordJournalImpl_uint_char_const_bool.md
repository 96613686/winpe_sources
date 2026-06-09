# CModule::RecordJournalImpl(uint,char const *,bool)

- ea: `0x18000c6b0`
- end: `0x18000c867`
- name: `?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z`
- size: `439`
- prototype: `void __fastcall(CModule *__hidden this, unsigned int, const char *, bool)`
- caller_count: `337`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004d30`
- `0x1800061f0`
- `0x1800062e0`
- `0x180006610`
- `0x1800067c8`
- `0x1800068d0`
- `0x180006fd0`
- `0x180007210`
- `0x180007290`
- `0x1800072d0`
- `0x1800076e0`
- `0x180007b54`
- `0x180007f40`
- `0x180008d40`
- `0x18000c1a0`
- `0x18000c870`
- `0x18000ceb0`
- `0x18000d180`
- `0x18000d1f0`
- `0x18000dfe0`
- `0x18000f6a0`
- `0x180010240`
- `0x180010598`
- `0x180010d80`
- `0x180011bf0`
- `0x180012260`
- `0x180012c70`
- `0x1800130f4`
- `0x1800131c0`
- `0x180013218`
- `0x180013cf4`
- `0x1800140f4`
- `0x180014284`
- `0x180014bb0`
- `0x180014df0`
- `0x180015578`
- `0x1800157fc`
- `0x180015ee0`
- `0x1800165e0`
- `0x18001a6f4`
- `0x18001ab8c`
- `0x18001e7f0`
- `0x18001f108`
- `0x18001f5f4`
- `0x18001fd2c`
- `0x18001fe84`
- `0x18001ff98`
- `0x1800202ac`
- `0x180020ad8`
- `0x18002132c`

## callees

- `0x18000c6b0`
- `0x18000e730`
- `0x180075fa0`
- `0x180076f20`
- `0x180092260`

## import_xrefs

- `ntdll!RtlCaptureStackBackTrace` at `0x18000c7a1`
- `ntdll!RtlCaptureStackBackTrace` at `0x18000c7a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c70b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c826`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c70b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c826`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000c716`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000c716`

## pseudocode

```c
void __fastcall CModule::RecordJournalImpl(CModule *this, int a2, const char *a3)
{
  unsigned int v5; // r14d
  __int64 v6; // rdi
  __int64 v7; // r8
  const char *v8; // r9
  __int64 v9; // rdx
  char *v10; // rcx
  char *v11; // rax
  unsigned int v12; // edx
  unsigned __int64 v13; // r10
  int v14; // eax
  unsigned __int64 v15; // r11
  unsigned int v16; // ebx
  __int64 v17; // rdx
  struct SJournalEntry *v18; // r8
  struct SJournalEntry *v19; // r9
  DWORD CurrentThreadId; // eax
  int v21; // edx
  int v22; // ecx
  PVOID BackTrace[50]; // [rsp+30h] [rbp-1C8h] BYREF

  v5 = ((unsigned __int8)_InterlockedExchangeAdd((volatile signed __int32 *)&JournalCounter, 0xFFFFFFFF) - 1) & 0x3F;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_DXGI_CompatShimLogging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DXGI_CompatShimLogging>::GetImpl'::`2'::impl);
  v6 = 120LL * v5;
  *(_DWORD *)((char *)&Journal + v6) = a2;
  *(_DWORD *)((char *)&Journal + v6 + 4) = GetCurrentThreadId();
  *(_DWORD *)((char *)&Journal + v6 + 8) = GetTickCount();
  v7 = 2147483646;
  *(_OWORD *)((char *)&Journal + v6 + 16) = 0;
  *(struct SJournalEntry near **)((char *)&Journal + v6 + 32) = 0;
  v8 = a3;
  *(struct SJournalEntry near **)((char *)&Journal + v6 + 40) = 0;
  v9 = 64;
  *(struct SJournalEntry near **)((char *)&Journal + v6 + 48) = 0;
  v10 = (char *)&Journal + v6 + 56;
  do
  {
    if ( !v7 )
      break;
    if ( !*v8 )
      break;
    *v10++ = *v8++;
    --v7;
    --v9;
  }
  while ( v9 );
  v11 = v10 - 1;
  if ( v9 )
    v11 = v10;
  *v11 = 0;
  memset_0(BackTrace, 0, sizeof(BackTrace));
  v12 = RtlCaptureStackBackTrace(1u, 0x32u, BackTrace, 0);
  if ( v12 >= 3 )
  {
    *(struct SJournalEntry near **)((char *)&Journal + v6 + 16) = (struct SJournalEntry near *)BackTrace[0];
    *(struct SJournalEntry near **)((char *)&Journal + v6 + 24) = (struct SJournalEntry near *)BackTrace[1];
    *(struct SJournalEntry near **)((char *)&Journal + v6 + 32) = (struct SJournalEntry near *)BackTrace[2];
  }
  v13 = qword_180109B50;
  v14 = 0;
  v15 = qword_180109B48;
  v16 = v12;
  do
  {
    v17 = (unsigned int)(v14 + 1);
    if ( (unsigned int)v17 >= v16 )
      break;
    v18 = (struct SJournalEntry *)BackTrace[v14];
    if ( (unsigned __int64)v18 >= v15 && (unsigned __int64)v18 <= v13 )
    {
      v19 = (struct SJournalEntry *)BackTrace[v17];
      if ( (unsigned __int64)v19 < v15 || (unsigned __int64)v19 > v13 )
      {
        *(struct SJournalEntry near **)((char *)&Journal + v6 + 40) = v18;
        ++v14;
        *(struct SJournalEntry near **)((char *)&Journal + v6 + 48) = v19;
      }
    }
    ++v14;
  }
  while ( (unsigned int)(v14 + 1) < 0x32 );
  if ( (Microsoft_Windows_DXGIEnableBits & 4) != 0 )
  {
    CurrentThreadId = GetCurrentThreadId();
    McTemplateU0qdqs_EtwEventWriteTransfer(v22, v21, v5, a2, CurrentThreadId, (__int64)a3);
  }
}

```

## disassembly

```asm
0x18000c6b0  mov     [rsp+arg_0], rbx
0x18000c6b5  push    rbp
0x18000c6b6  push    rsi
0x18000c6b7  push    rdi
0x18000c6b8  push    r14
0x18000c6ba  push    r15
0x18000c6bc  sub     rsp, 1D0h
0x18000c6c3  mov     rax, cs:__security_cookie
0x18000c6ca  xor     rax, rsp
0x18000c6cd  mov     [rsp+1F8h+var_38], rax
0x18000c6d5  mov     rbp, r8
0x18000c6d8  mov     esi, edx
0x18000c6da  mov     r14d, 0FFFFFFFFh
0x18000c6e0  lock xadd cs:?JournalCounter@@3IC, r14d; uint volatile JournalCounter
0x18000c6e9  dec     r14d
0x18000c6ec  and     r14d, 3Fh
0x18000c6f0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DXGI_CompatShimLogging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DXGI_CompatShimLogging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DXGI_CompatShimLogging> `wil::Feature<__WilFeatureTraits_Feature_DXGI_CompatShimLogging>::GetImpl(void)'::`2'::impl
0x18000c6f7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DXGI_CompatShimLogging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DXGI_CompatShimLogging>::__private_IsEnabled(void)
0x18000c6fc  imul    rdi, r14, 78h ; 'x'
0x18000c700  lea     r15, ?Journal@@3PAUSJournalEntry@@A; SJournalEntry near * Journal
0x18000c707  mov     [rdi+r15], esi
0x18000c70b  call    cs:__imp_GetCurrentThreadId
0x18000c711  mov     [rdi+r15+4], eax
0x18000c716  call    cs:__imp_GetTickCount
0x18000c71c  mov     [rdi+r15+8], eax
0x18000c721  xor     ebx, ebx
0x18000c723  xor     eax, eax
0x18000c725  lea     rcx, [r15+38h]
0x18000c729  xorps   xmm0, xmm0
0x18000c72c  mov     r8d, 7FFFFFFEh
0x18000c732  movups  xmmword ptr [rdi+r15+10h], xmm0
0x18000c738  mov     [rdi+r15+20h], rax
0x18000c73d  mov     r9, rbp
0x18000c740  mov     [rdi+r15+28h], rbx
0x18000c745  mov     edx, 40h ; '@'
0x18000c74a  mov     [rdi+r15+30h], rbx
0x18000c74f  add     rcx, rdi
0x18000c752  test    r8, r8
0x18000c755  jz      short loc_18000C770
0x18000c757  movzx   eax, byte ptr [r9]
0x18000c75b  test    al, al
0x18000c75d  jz      short loc_18000C770
0x18000c75f  mov     [rcx], al
0x18000c761  inc     r9
0x18000c764  inc     rcx
0x18000c767  dec     r8
0x18000c76a  sub     rdx, 1
0x18000c76e  jnz     short loc_18000C752
0x18000c770  test    rdx, rdx
0x18000c773  lea     rax, [rcx-1]
0x18000c777  mov     r8d, 190h; Size
0x18000c77d  cmovnz  rax, rcx
0x18000c781  xor     edx, edx; Val
0x18000c783  lea     rcx, [rsp+1F8h+BackTrace]; void *
0x18000c788  mov     [rax], bl
0x18000c78a  call    memset_0
0x18000c78f  xor     r9d, r9d; BackTraceHash
0x18000c792  lea     r8, [rsp+1F8h+BackTrace]; BackTrace
0x18000c797  mov     edx, 32h ; '2'; FramesToCapture
0x18000c79c  mov     ecx, 1; FramesToSkip
0x18000c7a1  call    cs:__imp_RtlCaptureStackBackTrace
0x18000c7a7  movzx   edx, ax
0x18000c7aa  cmp     edx, 3
0x18000c7ad  jb      short loc_18000C7CD
0x18000c7af  mov     rcx, [rsp+1F8h+BackTrace]
0x18000c7b4  mov     [rdi+r15+10h], rcx
0x18000c7b9  mov     rcx, [rsp+1F8h+var_1C0]
0x18000c7be  mov     [rdi+r15+18h], rcx
0x18000c7c3  mov     rcx, [rsp+1F8h+var_1B8]
0x18000c7c8  mov     [rdi+r15+20h], rcx
0x18000c7cd  mov     r10, cs:qword_180109B50
0x18000c7d4  mov     eax, ebx
0x18000c7d6  mov     r11, cs:qword_180109B48
0x18000c7dd  mov     ebx, edx
0x18000c7df  nop
0x18000c7e0  lea     edx, [rax+1]
0x18000c7e3  cmp     edx, ebx
0x18000c7e5  jnb     short loc_18000C81D
0x18000c7e7  mov     ecx, eax
0x18000c7e9  mov     r8, [rsp+rcx*8+1F8h+BackTrace]
0x18000c7ee  cmp     r8, r11
0x18000c7f1  jb      short loc_18000C813
0x18000c7f3  cmp     r8, r10
0x18000c7f6  ja      short loc_18000C813
0x18000c7f8  mov     r9, [rsp+rdx*8+1F8h+BackTrace]
0x18000c7fd  cmp     r9, r11
0x18000c800  jb      short loc_18000C807
0x18000c802  cmp     r9, r10
0x18000c805  jbe     short loc_18000C813
0x18000c807  mov     [rdi+r15+28h], r8
0x18000c80c  mov     eax, edx
0x18000c80e  mov     [rdi+r15+30h], r9
0x18000c813  inc     eax
0x18000c815  lea     ecx, [rax+1]
0x18000c818  cmp     ecx, 32h ; '2'
0x18000c81b  jb      short loc_18000C7E0
0x18000c81d  test    byte ptr cs:Microsoft_Windows_DXGIEnableBits, 4
0x18000c824  jz      short loc_18000C840
0x18000c826  call    cs:__imp_GetCurrentThreadId
0x18000c82c  mov     r9d, esi
0x18000c82f  mov     [rsp+1F8h+var_1D0], rbp
0x18000c834  mov     r8d, r14d
0x18000c837  mov     [rsp+1F8h+var_1D8], eax
0x18000c83b  call    McTemplateU0qdqs_EtwEventWriteTransfer
0x18000c840  mov     rcx, [rsp+1F8h+var_38]
0x18000c848  xor     rcx, rsp; StackCookie
0x18000c84b  call    __security_check_cookie
0x18000c850  mov     rbx, [rsp+1F8h+arg_0]
0x18000c858  add     rsp, 1D0h
0x18000c85f  pop     r15
0x18000c861  pop     r14
0x18000c863  pop     rdi
0x18000c864  pop     rsi
0x18000c865  pop     rbp
0x18000c866  retn
```
