# sub_1800CEBEC

- ea: `0x1800cebec`
- end: `0x1800cee93`
- name: `sub_1800CEBEC`
- size: `679`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800cb78c`

## callees

- `0x1800cc6c0`
- `0x1800cd3e4`
- `0x1800cebec`
- `0x1800cff14`
- `0x1800d16a4`
- `0x1800d2780`
- `0x1800d293c`
- `0x18017c160`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cec96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cec96`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800ced97`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800ced97`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800cee27`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800cee27`

## pseudocode

```c
void __fastcall sub_1800CEBEC(__int64 a1, unsigned int a2, __int64 a3, __int64 a4, int a5, __int64 a6, _DWORD *a7)
{
  int v9; // eax
  unsigned int v10; // eax
  __int64 v11; // rdx
  unsigned int v12; // ebx
  int v13; // ecx
  DWORD CurrentThreadId; // eax
  __int64 v15; // rcx
  bool v16; // zf
  _OWORD v17[10]; // [rsp+20h] [rbp-E0h] BYREF
  char v18; // [rsp+C0h] [rbp-40h]
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset(v17, 0, 0x98u);
  OutputString[0] = 0;
  v18 = 0;
  v9 = a7[1];
  DWORD2(v17[0]) = *a7;
  HIDWORD(v17[0]) = v9;
  v10 = sub_1800D16A4(DWORD2(v17[0]));
  v16 = *(_DWORD *)(v11 + 8) == 1;
  v12 = v10;
  LODWORD(v17[0]) = 1;
  v13 = 0;
  if ( v16 )
    v13 = 8;
  DWORD1(v17[0]) = v13;
  *((_QWORD *)&v17[1] + 1) = 0;
  LODWORD(v17[1]) = _InterlockedIncrement(&dword_1801F75B0);
  CurrentThreadId = GetCurrentThreadId();
  v17[4] = __PAIR64__(v12, a2);
  LODWORD(v17[2]) = CurrentThreadId;
  *((_QWORD *)&v17[3] + 1) = &qword_1801C79B8;
  *((_QWORD *)&v17[2] + 1) = 0;
  *(_QWORD *)&v17[3] = 0;
  *((_QWORD *)&v17[8] + 1) = a6;
  *(_QWORD *)&v17[9] = a1;
  memset(&v17[5], 0, 48);
  if ( qword_1801F74E0 )
    *(_QWORD *)&v17[8] = sub_18018C010();
  else
    *(_QWORD *)&v17[8] = 0;
  if ( qword_1801F7478 )
    sub_18018C010();
  if ( qword_1801F74A8 )
    sub_18018C010();
  if ( qword_1801F74A0 )
    sub_18018C010();
  if ( qword_1801F74C0 && (BYTE4(v17[0]) & 2) == 0 )
    sub_18018C010();
  if ( (SDWORD2(v17[0]) & 0x80000000) == 0 )
    sub_1800D293C(v15);
  if ( !byte_1801F7460
    && (!qword_1801F7450 ? (v16 = !IsDebuggerPresent()) : (v16 = (unsigned __int8)sub_18018C010() == 0), v16)
    || (BYTE4(v17[0]) & 2) != 0 )
  {
    if ( qword_1801F7468 && !byte_1801F7488 )
      sub_18018C010();
  }
  else
  {
    if ( qword_1801F7468 && !byte_1801F7488 )
      sub_18018C010();
    if ( !OutputString[0] )
      sub_1800CFF14(OutputString, 2048, v17);
    OutputDebugStringW(OutputString);
  }
  if ( ((BYTE4(v17[0]) & 4) != 0 || byte_1801F7470) && qword_1801F74B8 )
    sub_18018C010();
  if ( (BYTE4(v17[0]) & 1) != 0 )
    sub_1800D2780(v17);
}

```

## disassembly

```asm
0x1800cebec  mov     [rsp-8+arg_10], rbx
0x1800cebf1  push    rbp
0x1800cebf2  push    rsi
0x1800cebf3  push    rdi
0x1800cebf4  push    r14
0x1800cebf6  push    r15
0x1800cebf8  lea     rbp, [rsp-13D0h]
0x1800cec00  mov     eax, 14D0h
0x1800cec05  call    __alloca_probe
0x1800cec0a  sub     rsp, rax
0x1800cec0d  mov     rax, cs:__security_cookie
0x1800cec14  xor     rax, rsp
0x1800cec17  mov     [rbp+13F0h+var_30], rax
0x1800cec1e  mov     rdi, [rbp+13F0h+arg_28]
0x1800cec25  mov     esi, edx
0x1800cec27  mov     r14, rcx
0x1800cec2a  xor     edx, edx; Val
0x1800cec2c  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800cec31  mov     r8d, 98h; Size
0x1800cec37  call    memset
0x1800cec3c  mov     rdx, [rbp+13F0h+arg_30]
0x1800cec43  xor     r15d, r15d
0x1800cec46  mov     [rbp+13F0h+OutputString], r15w
0x1800cec4e  mov     [rbp+13F0h+var_1430], r15b
0x1800cec52  mov     ecx, [rdx]
0x1800cec54  mov     eax, [rdx+4]
0x1800cec57  mov     [rsp+14F0h+var_14C8], ecx
0x1800cec5b  mov     [rsp+14F0h+var_14C4], eax
0x1800cec5f  call    sub_1800D16A4
0x1800cec64  cmp     dword ptr [rdx+8], 1
0x1800cec68  mov     ebx, eax
0x1800cec6a  lea     eax, [r15+8]
0x1800cec6e  mov     [rsp+14F0h+var_14D0], 1
0x1800cec76  mov     ecx, r15d
0x1800cec79  cmovz   ecx, eax
0x1800cec7c  mov     [rsp+14F0h+var_14CC], ecx
0x1800cec80  lea     ecx, [rax-7]
0x1800cec83  lock xadd cs:dword_1801F75B0, ecx
0x1800cec8b  inc     ecx
0x1800cec8d  mov     [rsp+14F0h+var_14B8], r15
0x1800cec92  mov     [rsp+14F0h+var_14C0], ecx
0x1800cec96  call    cs:GetCurrentThreadId
0x1800cec9d  nop     dword ptr [rax+rax+00h]
0x1800ceca2  xorps   xmm0, xmm0
0x1800ceca5  mov     [rsp+14F0h+var_1490], esi
0x1800ceca9  mov     [rsp+14F0h+var_14B0], eax
0x1800cecad  xorps   xmm1, xmm1
0x1800cecb0  lea     rax, qword_1801C79B8
0x1800cecb7  mov     [rsp+14F0h+var_148C], ebx
0x1800cecbb  mov     [rsp+14F0h+var_1498], rax
0x1800cecc0  xor     eax, eax
0x1800cecc2  mov     [rbp+13F0h+var_1458], rax
0x1800cecc6  mov     [rbp+13F0h+var_1470], rax
0x1800cecca  mov     rax, cs:qword_1801F74E0
0x1800cecd1  mov     [rsp+14F0h+var_14A8], r15
0x1800cecd6  mov     [rsp+14F0h+var_14A0], r15
0x1800cecdb  mov     [rbp+13F0h+var_1448], rdi
0x1800cecdf  mov     [rbp+13F0h+var_1440], r14
0x1800cece3  mov     [rsp+14F0h+var_1488], r15
0x1800cece8  movups  [rbp+13F0h+var_1468], xmm0
0x1800cecec  movups  [rsp+14F0h+var_1480], xmm1
0x1800cecf1  test    rax, rax
0x1800cecf4  jz      short loc_1800CED01
0x1800cecf6  call    sub_18018C010
0x1800cecfb  mov     [rbp+13F0h+var_1450], rax
0x1800cecff  jmp     short loc_1800CED05
0x1800ced01  mov     [rbp+13F0h+var_1450], r15
0x1800ced05  mov     rax, cs:qword_1801F7478
0x1800ced0c  test    rax, rax
0x1800ced0f  jz      short loc_1800CED1B
0x1800ced11  lea     rcx, [rsp+14F0h+var_14D0]
0x1800ced16  call    sub_18018C010
0x1800ced1b  mov     rax, cs:qword_1801F74A8
0x1800ced22  test    rax, rax
0x1800ced25  jz      short loc_1800CED3B
0x1800ced27  mov     r8d, 400h
0x1800ced2d  lea     rdx, [rbp+13F0h+var_1430]
0x1800ced31  lea     rcx, [rsp+14F0h+var_14D0]
0x1800ced36  call    sub_18018C010
0x1800ced3b  mov     rax, cs:qword_1801F74A0
0x1800ced42  test    rax, rax
0x1800ced45  jz      short loc_1800CED51
0x1800ced47  lea     rcx, [rsp+14F0h+var_14D0]
0x1800ced4c  call    sub_18018C010
0x1800ced51  mov     rax, cs:qword_1801F74C0
0x1800ced58  test    rax, rax
0x1800ced5b  jz      short loc_1800CED6E
0x1800ced5d  test    byte ptr [rsp+14F0h+var_14CC], 2
0x1800ced62  jnz     short loc_1800CED6E
0x1800ced64  lea     rcx, [rsp+14F0h+var_14D0]
0x1800ced69  call    sub_18018C010
0x1800ced6e  cmp     [rsp+14F0h+var_14C8], r15d
0x1800ced73  jge     loc_1800CEE82
0x1800ced79  cmp     cs:byte_1801F7460, r15b
0x1800ced80  jnz     short loc_1800CEDA7
0x1800ced82  mov     rax, cs:qword_1801F7450
0x1800ced89  test    rax, rax
0x1800ced8c  jz      short loc_1800CED97
0x1800ced8e  call    sub_18018C010
0x1800ced93  test    al, al
0x1800ced95  jmp     short loc_1800CEDA5
0x1800ced97  call    cs:IsDebuggerPresent
0x1800ced9e  nop     dword ptr [rax+rax+00h]
0x1800ceda3  test    eax, eax
0x1800ceda5  jz      short loc_1800CEDAE
0x1800ceda7  test    byte ptr [rsp+14F0h+var_14CC], 2
0x1800cedac  jz      short loc_1800CEDD4
0x1800cedae  mov     rax, cs:qword_1801F7468
0x1800cedb5  test    rax, rax
0x1800cedb8  jz      short loc_1800CEE33
0x1800cedba  cmp     cs:byte_1801F7488, r15b
0x1800cedc1  jnz     short loc_1800CEE33
0x1800cedc3  xor     r8d, r8d
0x1800cedc6  lea     rcx, [rsp+14F0h+var_14D0]
0x1800cedcb  xor     edx, edx
0x1800cedcd  call    sub_18018C010
0x1800cedd2  jmp     short loc_1800CEE33
0x1800cedd4  mov     rax, cs:qword_1801F7468
0x1800ceddb  mov     ebx, 800h
0x1800cede0  test    rax, rax
0x1800cede3  jz      short loc_1800CEE02
0x1800cede5  cmp     cs:byte_1801F7488, r15b
0x1800cedec  jnz     short loc_1800CEE02
0x1800cedee  mov     r8d, ebx
0x1800cedf1  lea     rdx, [rbp+13F0h+OutputString]
0x1800cedf8  lea     rcx, [rsp+14F0h+var_14D0]
0x1800cedfd  call    sub_18018C010
0x1800cee02  cmp     [rbp+13F0h+OutputString], r15w
0x1800cee0a  jnz     short loc_1800CEE20
0x1800cee0c  lea     r8, [rsp+14F0h+var_14D0]
0x1800cee11  mov     rdx, rbx
0x1800cee14  lea     rcx, [rbp+13F0h+OutputString]
0x1800cee1b  call    sub_1800CFF14
0x1800cee20  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800cee27  call    cs:OutputDebugStringW
0x1800cee2e  nop     dword ptr [rax+rax+00h]
0x1800cee33  test    byte ptr [rsp+14F0h+var_14CC], 4
0x1800cee38  jnz     short loc_1800CEE43
0x1800cee3a  cmp     cs:byte_1801F7470, r15b
0x1800cee41  jz      short loc_1800CEE54
0x1800cee43  mov     rax, cs:qword_1801F74B8
0x1800cee4a  test    rax, rax
0x1800cee4d  jz      short loc_1800CEE54
0x1800cee4f  call    sub_18018C010
0x1800cee54  test    byte ptr [rsp+14F0h+var_14CC], 1
0x1800cee59  jnz     short loc_1800CEE88
0x1800cee5b  mov     rcx, [rbp+13F0h+var_30]
0x1800cee62  xor     rcx, rsp; StackCookie
0x1800cee65  call    __security_check_cookie
0x1800cee6a  mov     rbx, [rsp+14F0h+arg_10]
0x1800cee72  add     rsp, 14D0h
0x1800cee79  pop     r15
0x1800cee7b  pop     r14
0x1800cee7d  pop     rdi
0x1800cee7e  pop     rsi
0x1800cee7f  pop     rbp
0x1800cee80  retn
0x1800cee82  call    sub_1800D293C
0x1800cee88  lea     rcx, [rsp+14F0h+var_14D0]
0x1800cee8d  call    sub_1800D2780
```
