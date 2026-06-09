# CircularLog::Init(ushort const *,ushort const *,ulong)

- ea: `0x14001070c`
- end: `0x140010938`
- name: `?Init@CircularLog@@QEAA_NPEBG0K@Z`
- size: `556`
- prototype: `char __fastcall(CircularLog *this, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140006188`

## callees

- `0x140001100`
- `0x1400012c0`
- `0x14000a10c`
- `0x14000ad80`
- `0x14001070c`
- `0x140010ba8`
- `0x140010c68`

## string_xrefs

- `0x14001089c`: `To learn about increasing the verbosity of the NGen log files please see http://go.microsoft.com/fwlink/?linkid=210113\n`

## pseudocode

```c
char __fastcall CircularLog::Init(CircularLog *this, const unsigned __int16 *a2, const unsigned __int16 *a3, int a4)
{
  void *v6; // r8
  int *v7; // r9
  int v9; // [rsp+20h] [rbp-20h] BYREF
  int v10; // [rsp+24h] [rbp-1Ch]
  int v11; // [rsp+28h] [rbp-18h]
  void *lpMem; // [rsp+30h] [rbp-10h]

  g_MachineWideLogger = 0;
  v9 = 2;
  v10 = 2;
  v11 = 16;
  lpMem = (void *)&SString::s_EmptyBuffer;
  SString::Set((SString *)&v9, a2);
  SBuffer::Set((SBuffer *)&qword_140027068, (const struct SBuffer *)&v9);
  dword_140027070 = v11 & 7 | dword_140027070 & 0xFFFFFEF8;
  if ( (v11 & 8) != 0 )
    operator delete(lpMem);
  SString::Append((SString *)&qword_140027068, L".log");
  v9 = 2;
  v10 = 2;
  v11 = 16;
  lpMem = (void *)&SString::s_EmptyBuffer;
  SString::Set((SString *)&v9, a2);
  SBuffer::Set((SBuffer *)&dword_1400270B0, (const struct SBuffer *)&v9);
  dword_1400270B8 = v11 & 7 | dword_1400270B8 & 0xFFFFFEF8;
  if ( (v11 & 8) != 0 )
    operator delete(lpMem);
  SString::Append((SString *)&dword_1400270B0, L".lock");
  v9 = 2;
  v10 = 2;
  v11 = 16;
  lpMem = (void *)&SString::s_EmptyBuffer;
  SString::Set((SString *)&v9, a2);
  SBuffer::Set((SBuffer *)&dword_140027098, (const struct SBuffer *)&v9);
  dword_1400270A0 = v11 & 7 | dword_1400270A0 & 0xFFFFFEF8;
  if ( (v11 & 8) != 0 )
    operator delete(lpMem);
  SString::Append((SString *)&dword_140027098, L".old.log");
  v9 = 2;
  v10 = 2;
  v11 = 16;
  lpMem = (void *)&SString::s_EmptyBuffer;
  SString::Set(
    (SString *)&v9,
    L"To learn about increasing the verbosity of the NGen log files please see http://go.microsoft.com/fwlink/?linkid=210113\r\n");
  SBuffer::Set((SBuffer *)&dword_140027080, (const struct SBuffer *)&v9);
  dword_140027088 = v11 & 7 | dword_140027088 & 0xFFFFFEF8;
  if ( (v11 & 8) != 0 )
    operator delete(lpMem);
  dword_1400270C8 = a4;
  dword_1400270CC = 0;
  g_MachineWideLogger = 1;
  if ( (unsigned int)CircularLog::CheckLogHeader((CircularLog *)&g_MachineWideLogger) )
    CircularLog::CheckForLogReset((CircularLog *)&g_MachineWideLogger, 0, v6, v7);
  return 1;
}

```

## disassembly

```asm
0x14001070c  mov     rax, rsp
0x14001070f  mov     [rax+8], rbx
0x140010713  mov     [rax+10h], rsi
0x140010717  mov     [rax+18h], rdi
0x14001071b  mov     [rax+20h], r12
0x14001071f  push    rbp
0x140010720  push    r13
0x140010722  push    r15
0x140010724  mov     rbp, rsp
0x140010727  sub     rsp, 40h
0x14001072b  mov     edi, r9d
0x14001072e  mov     rbx, rdx
0x140010731  mov     cs:?g_MachineWideLogger@@3VMachineWideLogger@@A, 0; MachineWideLogger g_MachineWideLogger
0x140010738  mov     esi, 2
0x14001073d  mov     [rbp+var_20], esi
0x140010740  mov     [rbp+var_1C], esi
0x140010743  mov     [rbp+var_18], 10h
0x14001074a  lea     r15, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x140010751  mov     [rbp+lpMem], r15
0x140010755  lea     rcx, [rbp+var_20]; this
0x140010759  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x14001075e  nop
0x14001075f  lea     rdx, [rbp+var_20]; struct SBuffer *
0x140010763  lea     rcx, qword_140027068; this
0x14001076a  call    ?Set@SBuffer@@QEAAXAEBV1@@Z; SBuffer::Set(SBuffer const &)
0x14001076f  mov     eax, [rbp+var_18]
0x140010772  and     eax, 7
0x140010775  mov     ecx, cs:dword_140027070
0x14001077b  mov     r12d, 0FFFFFFF8h
0x140010781  and     ecx, r12d
0x140010784  or      ecx, eax
0x140010786  mov     r13d, 0FFFFFEFFh
0x14001078c  and     ecx, r13d
0x14001078f  mov     cs:dword_140027070, ecx
0x140010795  test    byte ptr [rbp+var_18], 8
0x140010799  jz      short loc_1400107A4
0x14001079b  mov     rcx, [rbp+lpMem]; lpMem
0x14001079f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400107a4  lea     rdx, aLog; ".log"
0x1400107ab  lea     rcx, qword_140027068; this
0x1400107b2  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x1400107b7  mov     [rbp+var_20], esi
0x1400107ba  mov     [rbp+var_1C], esi
0x1400107bd  mov     [rbp+var_18], 10h
0x1400107c4  mov     [rbp+lpMem], r15
0x1400107c8  mov     rdx, rbx; unsigned __int16 *
0x1400107cb  lea     rcx, [rbp+var_20]; this
0x1400107cf  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x1400107d4  nop
0x1400107d5  lea     rdx, [rbp+var_20]; struct SBuffer *
0x1400107d9  lea     rcx, dword_1400270B0; this
0x1400107e0  call    ?Set@SBuffer@@QEAAXAEBV1@@Z; SBuffer::Set(SBuffer const &)
0x1400107e5  mov     eax, [rbp+var_18]
0x1400107e8  and     eax, 7
0x1400107eb  mov     edx, cs:dword_1400270B8
0x1400107f1  and     edx, r12d
0x1400107f4  or      edx, eax
0x1400107f6  and     edx, r13d
0x1400107f9  mov     cs:dword_1400270B8, edx
0x1400107ff  test    byte ptr [rbp+var_18], 8
0x140010803  jz      short loc_14001080E
0x140010805  mov     rcx, [rbp+lpMem]; lpMem
0x140010809  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14001080e  lea     rdx, aLock; ".lock"
0x140010815  lea     rcx, dword_1400270B0; this
0x14001081c  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x140010821  mov     [rbp+var_20], esi
0x140010824  mov     [rbp+var_1C], esi
0x140010827  mov     [rbp+var_18], 10h
0x14001082e  mov     [rbp+lpMem], r15
0x140010832  mov     rdx, rbx; unsigned __int16 *
0x140010835  lea     rcx, [rbp+var_20]; this
0x140010839  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x14001083e  nop
0x14001083f  lea     rdx, [rbp+var_20]; struct SBuffer *
0x140010843  lea     rcx, dword_140027098; this
0x14001084a  call    ?Set@SBuffer@@QEAAXAEBV1@@Z; SBuffer::Set(SBuffer const &)
0x14001084f  mov     eax, [rbp+var_18]
0x140010852  and     eax, 7
0x140010855  mov     edx, cs:dword_1400270A0
0x14001085b  and     edx, r12d
0x14001085e  or      edx, eax
0x140010860  and     edx, r13d
0x140010863  mov     cs:dword_1400270A0, edx
0x140010869  test    byte ptr [rbp+var_18], 8
0x14001086d  jz      short loc_140010878
0x14001086f  mov     rcx, [rbp+lpMem]; lpMem
0x140010873  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140010878  lea     rdx, aOldLog; ".old.log"
0x14001087f  lea     rcx, dword_140027098; this
0x140010886  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x14001088b  mov     [rbp+var_20], esi
0x14001088e  mov     [rbp+var_1C], esi
0x140010891  mov     [rbp+var_18], 10h
0x140010898  mov     [rbp+lpMem], r15
0x14001089c  lea     rdx, aToLearnAboutIn; "To learn about increasing the verbosity"...
0x1400108a3  lea     rcx, [rbp+var_20]; this
0x1400108a7  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x1400108ac  nop
0x1400108ad  lea     rdx, [rbp+var_20]; struct SBuffer *
0x1400108b1  lea     rcx, dword_140027080; this
0x1400108b8  call    ?Set@SBuffer@@QEAAXAEBV1@@Z; SBuffer::Set(SBuffer const &)
0x1400108bd  mov     eax, [rbp+var_18]
0x1400108c0  and     eax, 7
0x1400108c3  mov     ecx, cs:dword_140027088
0x1400108c9  and     ecx, r12d
0x1400108cc  or      ecx, eax
0x1400108ce  and     ecx, r13d
0x1400108d1  mov     cs:dword_140027088, ecx
0x1400108d7  test    byte ptr [rbp+var_18], 8
0x1400108db  jz      short loc_1400108E6
0x1400108dd  mov     rcx, [rbp+lpMem]; lpMem
0x1400108e1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400108e6  mov     cs:dword_1400270C8, edi
0x1400108ec  and     cs:dword_1400270CC, 0
0x1400108f3  mov     cs:?g_MachineWideLogger@@3VMachineWideLogger@@A, 1; MachineWideLogger g_MachineWideLogger
0x1400108fa  lea     rcx, ?g_MachineWideLogger@@3VMachineWideLogger@@A; this
0x140010901  call    ?CheckLogHeader@CircularLog@@IEAAHXZ; CircularLog::CheckLogHeader(void)
0x140010906  test    eax, eax
0x140010908  jz      short loc_140010918
0x14001090a  xor     edx, edx; int
0x14001090c  lea     rcx, ?g_MachineWideLogger@@3VMachineWideLogger@@A; this
0x140010913  call    ?CheckForLogReset@CircularLog@@IEAAXH@Z; CircularLog::CheckForLogReset(int)
0x140010918  mov     al, 1
0x14001091a  mov     rbx, [rsp+40h+arg_0]
0x14001091f  mov     rsi, [rsp+40h+arg_8]
0x140010924  mov     rdi, [rsp+40h+arg_10]
0x140010929  mov     r12, [rsp+40h+arg_18]
0x14001092e  add     rsp, 40h
0x140010932  pop     r15
0x140010934  pop     r13
0x140010936  pop     rbp
0x140010937  retn
```
