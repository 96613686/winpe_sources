# BiUpdateEfiEntry

- ea: `0x180038034`
- end: `0x180038256`
- name: `BiUpdateEfiEntry`
- size: `546`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callers

- `0x180036364`
- `0x180036c88`

## callees

- `0x180003ba9`
- `0x18002d588`
- `0x18002e4a8`
- `0x18002e4fc`
- `0x180034254`
- `0x180036540`
- `0x180037abc`
- `0x180038034`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180038174`
- `ntdll!RtlFreeHeap` at `0x1800381b7`
- `ntdll!RtlFreeHeap` at `0x1800381da`
- `ntdll!RtlFreeHeap` at `0x1800381fd`
- `ntdll!RtlFreeHeap` at `0x18003823d`
- `ntdll!RtlFreeHeap` at `0x180038174`
- `ntdll!RtlFreeHeap` at `0x1800381b7`
- `ntdll!RtlFreeHeap` at `0x1800381da`
- `ntdll!RtlFreeHeap` at `0x1800381fd`
- `ntdll!RtlFreeHeap` at `0x18003823d`

## string_xrefs

- `0x180038184`: `BiUpdateEfiEntry %d '%ws' failed 0x%x`

## pseudocode

```c
__int64 __fastcall BiUpdateEfiEntry(unsigned __int64 a1, __int64 a2)
{
  _DWORD *v2; // rdi
  PVOID v4; // r15
  _DWORD *v5; // r13
  _WORD *v6; // r12
  int v7; // ebx
  int v8; // eax
  void *v9; // rsi
  unsigned int v10; // eax
  __int64 v12; // [rsp+20h] [rbp-40h]
  int v13; // [rsp+30h] [rbp-30h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-28h] BYREF
  _DWORD *v15; // [rsp+40h] [rbp-20h] BYREF
  _WORD *v16; // [rsp+48h] [rbp-18h] BYREF
  PVOID P; // [rsp+50h] [rbp-10h] BYREF
  void *Buf2; // [rsp+58h] [rbp-8h] BYREF
  int v20; // [rsp+B0h] [rbp+50h] BYREF
  int v21; // [rsp+B8h] [rbp+58h] BYREF

  v2 = *(_DWORD **)(a2 + 40);
  v20 = 0;
  v21 = 0;
  v4 = 0;
  v13 = 0;
  v5 = 0;
  P = 0;
  v6 = 0;
  v15 = 0;
  v16 = 0;
  Buf2 = 0;
  Handle = 0;
  v7 = BcdOpenObject(a1, (_QWORD *)(a2 + 16), &Handle);
  if ( v7 < 0 )
    goto LABEL_11;
  BiGetElement(Handle, 301989892, &P, &v20);
  if ( (*(_BYTE *)(a2 + 48) & 8) == 0 )
  {
    BiGetElement(Handle, 285212673, &v15, &v21);
    BiGetElement(Handle, 301989890, &v16, &v13);
    v5 = v15;
    v6 = v16;
  }
  v4 = P;
  v8 = BiCreateMergedBootEntry(v2, P, v5, v6, &Buf2);
  v7 = v8;
  if ( v8 == -1073741766 )
  {
    v7 = 0;
    goto LABEL_12;
  }
  if ( v8 < 0 )
    goto LABEL_11;
  v9 = Buf2;
  v10 = v2[1];
  if ( v10 != *((_DWORD *)Buf2 + 1) || memcmp_0(v2, Buf2, v10) )
  {
    BiLogMessage(2, L"Updating BootEntry: %d '%ws'", (unsigned int)v2[2], (char *)v2 + (unsigned int)v2[4]);
    v7 = BiModifyBootEntry(v9);
    if ( v7 < 0 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
LABEL_11:
      LODWORD(v12) = v7;
      BiLogMessage(
        4,
        L"BiUpdateEfiEntry %d '%ws' failed 0x%x",
        (unsigned int)v2[2],
        (char *)v2 + (unsigned int)v2[4],
        v12);
      goto LABEL_12;
    }
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
  *(_QWORD *)(a2 + 40) = v9;
LABEL_12:
  if ( v4 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  if ( v5 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  if ( v6 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  if ( Handle )
    BcdCloseObject(Handle);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180038034  mov     [rsp-38h+arg_8], rdx
0x180038039  push    rbp
0x18003803a  push    rbx
0x18003803b  push    rsi
0x18003803c  push    rdi
0x18003803d  push    r12
0x18003803f  push    r13
0x180038041  push    r15
0x180038043  mov     rbp, rsp
0x180038046  sub     rsp, 60h
0x18003804a  mov     rdi, [rdx+28h]
0x18003804e  lea     r8, [rbp+Handle]
0x180038052  xor     eax, eax
0x180038054  mov     rsi, rdx
0x180038057  add     rdx, 10h
0x18003805b  mov     [rbp+arg_10], eax
0x18003805e  mov     [rbp+arg_18], eax
0x180038061  mov     r15d, eax
0x180038064  mov     [rbp+var_30], eax
0x180038067  mov     r13d, eax
0x18003806a  mov     [rbp+P], rax
0x18003806e  mov     r12d, eax
0x180038071  mov     [rbp+var_20], rax
0x180038075  mov     [rbp+var_18], rax
0x180038079  mov     [rbp+Buf2], rax
0x18003807d  mov     [rbp+Handle], rax
0x180038081  call    BcdOpenObject
0x180038086  mov     ebx, eax
0x180038088  test    eax, eax
0x18003808a  js      loc_180038180
0x180038090  mov     rcx, [rbp+Handle]
0x180038094  lea     r9, [rbp+arg_10]
0x180038098  lea     r8, [rbp+P]
0x18003809c  mov     edx, 12000004h
0x1800380a1  call    BiGetElement
0x1800380a6  test    byte ptr [rsi+30h], 8
0x1800380aa  jnz     short loc_1800380E0
0x1800380ac  mov     rcx, [rbp+Handle]
0x1800380b0  lea     r9, [rbp+arg_18]
0x1800380b4  lea     r8, [rbp+var_20]
0x1800380b8  mov     edx, 11000001h
0x1800380bd  call    BiGetElement
0x1800380c2  mov     rcx, [rbp+Handle]
0x1800380c6  lea     r9, [rbp+var_30]
0x1800380ca  lea     r8, [rbp+var_18]
0x1800380ce  mov     edx, 12000002h
0x1800380d3  call    BiGetElement
0x1800380d8  mov     r13, [rbp+var_20]
0x1800380dc  mov     r12, [rbp+var_18]
0x1800380e0  mov     r15, [rbp+P]
0x1800380e4  lea     rax, [rbp+Buf2]
0x1800380e8  mov     rdx, r15
0x1800380eb  mov     [rsp+60h+var_40], rax
0x1800380f0  mov     r9, r12
0x1800380f3  mov     r8, r13
0x1800380f6  mov     rcx, rdi
0x1800380f9  call    BiCreateMergedBootEntry
0x1800380fe  mov     ebx, eax
0x180038100  cmp     eax, 0C000003Ah
0x180038105  jnz     short loc_18003810E
0x180038107  xor     ebx, ebx
0x180038109  jmp     loc_1800381A0
0x18003810e  test    eax, eax
0x180038110  js      short loc_180038180
0x180038112  mov     rsi, [rbp+Buf2]
0x180038116  mov     eax, [rdi+4]
0x180038119  cmp     eax, [rsi+4]
0x18003811c  jnz     short loc_180038134
0x18003811e  mov     r8d, eax; Size
0x180038121  mov     rdx, rsi; Buf2
0x180038124  mov     rcx, rdi; Buf1
0x180038127  call    memcmp_0
0x18003812c  test    eax, eax
0x18003812e  jz      loc_18003822B
0x180038134  mov     r9d, [rdi+10h]
0x180038138  lea     rdx, aUpdatingBooten; "Updating BootEntry: %d '%ws'"
0x18003813f  mov     r8d, [rdi+8]
0x180038143  add     r9, rdi
0x180038146  mov     ecx, 2
0x18003814b  call    BiLogMessage
0x180038150  mov     rcx, rsi
0x180038153  call    BiModifyBootEntry
0x180038158  mov     ebx, eax
0x18003815a  test    eax, eax
0x18003815c  jns     loc_18003822B
0x180038162  mov     rcx, gs:60h
0x18003816b  mov     r8, rsi; P
0x18003816e  xor     edx, edx; Flags
0x180038170  mov     rcx, [rcx+30h]; HeapHandle
0x180038174  call    cs:__imp_RtlFreeHeap
0x18003817b  nop     dword ptr [rax+rax+00h]
0x180038180  mov     r9d, [rdi+10h]
0x180038184  lea     rdx, aBiupdateefient; "BiUpdateEfiEntry %d '%ws' failed 0x%x"
0x18003818b  mov     r8d, [rdi+8]
0x18003818f  add     r9, rdi
0x180038192  mov     ecx, 4
0x180038197  mov     dword ptr [rsp+60h+var_40], ebx
0x18003819b  call    BiLogMessage
0x1800381a0  test    r15, r15
0x1800381a3  jz      short loc_1800381C3
0x1800381a5  mov     rcx, gs:60h
0x1800381ae  mov     r8, r15; P
0x1800381b1  xor     edx, edx; Flags
0x1800381b3  mov     rcx, [rcx+30h]; HeapHandle
0x1800381b7  call    cs:__imp_RtlFreeHeap
0x1800381be  nop     dword ptr [rax+rax+00h]
0x1800381c3  test    r13, r13
0x1800381c6  jz      short loc_1800381E6
0x1800381c8  mov     rcx, gs:60h
0x1800381d1  mov     r8, r13; P
0x1800381d4  xor     edx, edx; Flags
0x1800381d6  mov     rcx, [rcx+30h]; HeapHandle
0x1800381da  call    cs:__imp_RtlFreeHeap
0x1800381e1  nop     dword ptr [rax+rax+00h]
0x1800381e6  test    r12, r12
0x1800381e9  jz      short loc_180038209
0x1800381eb  mov     rcx, gs:60h
0x1800381f4  mov     r8, r12; P
0x1800381f7  xor     edx, edx; Flags
0x1800381f9  mov     rcx, [rcx+30h]; HeapHandle
0x1800381fd  call    cs:__imp_RtlFreeHeap
0x180038204  nop     dword ptr [rax+rax+00h]
0x180038209  cmp     [rbp+Handle], 0
0x18003820e  jz      short loc_180038219
0x180038210  mov     rcx, [rbp+Handle]; Handle
0x180038214  call    BcdCloseObject
0x180038219  mov     eax, ebx
0x18003821b  add     rsp, 60h
0x18003821f  pop     r15
0x180038221  pop     r13
0x180038223  pop     r12
0x180038225  pop     rdi
0x180038226  pop     rsi
0x180038227  pop     rbx
0x180038228  pop     rbp
0x180038229  retn
0x18003822b  mov     rcx, gs:60h
0x180038234  mov     r8, rdi; P
0x180038237  xor     edx, edx; Flags
0x180038239  mov     rcx, [rcx+30h]; HeapHandle
0x18003823d  call    cs:__imp_RtlFreeHeap
0x180038244  nop     dword ptr [rax+rax+00h]
0x180038249  mov     rax, [rbp+arg_8]
0x18003824d  mov     [rax+28h], rsi
0x180038251  jmp     loc_1800381A0
```
