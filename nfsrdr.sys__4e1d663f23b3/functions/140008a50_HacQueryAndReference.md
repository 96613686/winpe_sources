# HacQueryAndReference

- ea: `0x140008a50`
- end: `0x140008cad`
- name: `HacQueryAndReference`
- size: `605`
- prototype: `__int64 *__fastcall(PRKMUTEX Mutex, PCUNICODE_STRING String2)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140004530`
- `0x1400070a0`
- `0x140008680`
- `0x1400146a0`
- `0x140019044`
- `0x140020884`
- `0x140020af4`

## callees

- `0x140008a50`
- `0x1400173f8`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x140008afb`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140008afb`
- `ntoskrnl!KeWaitForSingleObject` at `0x140008a70`
- `ntoskrnl!KeWaitForSingleObject` at `0x140008b21`
- `ntoskrnl!KeWaitForSingleObject` at `0x140008a70`
- `ntoskrnl!KeWaitForSingleObject` at `0x140008b21`
- `ntoskrnl!KeReleaseMutex` at `0x140008b46`
- `ntoskrnl!KeReleaseMutex` at `0x140008b57`
- `ntoskrnl!KeReleaseMutex` at `0x140008b46`
- `ntoskrnl!KeReleaseMutex` at `0x140008b57`

## pseudocode

```c
__int64 *__fastcall HacQueryAndReference(PRKMUTEX Mutex, PCUNICODE_STRING String2)
{
  unsigned int v4; // r10d
  volatile unsigned int Lock; // ebx
  unsigned int Length; // ecx
  PWSTR Buffer; // rdx
  unsigned int v8; // r9d
  unsigned int v9; // eax
  unsigned int j; // r8d
  int v11; // ecx
  unsigned int v12; // edx
  __int64 *k; // rbx
  __int64 v14; // rdx
  __int64 v16; // rax
  __int64 v17; // rcx
  unsigned int i; // ebp
  __int64 v19; // r14
  volatile unsigned int v20; // r8d

  KeWaitForSingleObject(Mutex, Executive, 0, 0, 0);
  v4 = dword_1400411C4;
  Lock = Mutex[1].Header.Lock;
  if ( !dword_1400411C4 || dword_1400411C4 > Lock )
  {
    for ( i = 15; ; --i )
    {
      if ( !i )
      {
        v4 = dword_1400411C4;
        goto LABEL_3;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
      {
        WPP_SF_dd(
          WPP_GLOBAL_Control->AttachedDevice,
          10,
          WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids,
          i,
          *((_DWORD *)PowerOf2Primes + i));
      }
      v19 = 4LL * i;
      v20 = *(_DWORD *)((char *)PowerOf2Primes + v19);
      if ( v20 < Lock )
        break;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
      WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids, Lock, v20);
    v4 = *(_DWORD *)((char *)PowerOf2Primes + v19);
    dword_1400411C4 = v4;
  }
LABEL_3:
  Length = String2->Length;
  if ( !(_WORD)Length )
    goto LABEL_17;
  Buffer = String2->Buffer;
  v8 = Length >> 1;
  v9 = 0;
  for ( j = 0; j < v8; v9 = __ROR4__(v11 ^ v9, 27) )
  {
    v11 = *Buffer++;
    ++j;
  }
  if ( v4 )
    v12 = v9 % v4;
  else
LABEL_17:
    v12 = 0;
  for ( k = (__int64 *)*((_QWORD *)&Mutex[2].Header.WaitListHead.Flink->Flink + v12); k; k = (__int64 *)*k )
  {
    if ( !RtlCompareUnicodeString((PCUNICODE_STRING)k + 4, String2, 0) )
    {
      KeWaitForSingleObject((PVOID)k[5], Executive, 0, 0, 0);
      v14 = k[5];
      if ( *(_QWORD *)(v14 + 88) )
      {
        if ( *(__int64 **)(v14 + 96) != k )
        {
          v16 = k[2];
          if ( v16 )
          {
            v17 = k[3];
            if ( v17 )
            {
              *(_QWORD *)(v17 + 16) = v16;
              *(_QWORD *)(k[2] + 24) = k[3];
            }
            else
            {
              *(_QWORD *)(v14 + 88) = v16;
              *(_QWORD *)(k[2] + 24) = 0;
            }
          }
          *(_QWORD *)(*(_QWORD *)(v14 + 96) + 16LL) = k;
          k[3] = *(_QWORD *)(v14 + 96);
          k[2] = 0;
          *(_QWORD *)(v14 + 96) = k;
        }
      }
      else
      {
        *(_QWORD *)(v14 + 88) = k;
        *(_QWORD *)(v14 + 96) = k;
      }
      ++*((_DWORD *)k + 13);
      KeReleaseMutex((PRKMUTEX)k[5], 0);
      break;
    }
  }
  KeReleaseMutex(Mutex, 0);
  return k;
}

```

## disassembly

```asm
0x140008a50  push    rbx
0x140008a52  push    rsi
0x140008a53  push    rdi
0x140008a54  push    r15
0x140008a56  sub     rsp, 38h
0x140008a5a  mov     rsi, rdx
0x140008a5d  xor     r15d, r15d
0x140008a60  xor     edx, edx; WaitReason
0x140008a62  mov     [rsp+58h+Timeout], r15; Timeout
0x140008a67  xor     r9d, r9d; Alertable
0x140008a6a  xor     r8d, r8d; WaitMode
0x140008a6d  mov     rdi, rcx
0x140008a70  call    cs:__imp_KeWaitForSingleObject
0x140008a77  nop     dword ptr [rax+rax+00h]
0x140008a7c  mov     r10d, cs:dword_1400411C4
0x140008a83  mov     ebx, [rdi+38h]
0x140008a86  test    r10d, r10d
0x140008a89  jz      loc_140008BD0
0x140008a8f  cmp     r10d, ebx
0x140008a92  ja      loc_140008BD0
0x140008a98  movzx   ecx, word ptr [rsi]
0x140008a9b  test    cx, cx
0x140008a9e  jz      loc_140008B7B
0x140008aa4  mov     rdx, [rsi+8]
0x140008aa8  mov     r9d, ecx
0x140008aab  shr     r9d, 1
0x140008aae  mov     eax, r15d
0x140008ab1  mov     r8d, r15d
0x140008ab4  jz      short loc_140008AD4
0x140008ab6  nop     word ptr [rax+rax+00000000h]
0x140008ac0  movzx   ecx, word ptr [rdx]
0x140008ac3  lea     rdx, [rdx+2]
0x140008ac7  xor     eax, ecx
0x140008ac9  inc     r8d
0x140008acc  ror     eax, 1Bh
0x140008acf  cmp     r8d, r9d
0x140008ad2  jb      short loc_140008AC0
0x140008ad4  test    r10d, r10d
0x140008ad7  jz      loc_140008B7B
0x140008add  xor     edx, edx
0x140008adf  div     r10d
0x140008ae2  mov     rax, [rdi+78h]
0x140008ae6  mov     ecx, edx
0x140008ae8  mov     rbx, [rax+rcx*8]
0x140008aec  test    rbx, rbx
0x140008aef  jz      short loc_140008B52
0x140008af1  lea     rcx, [rbx+40h]; String1
0x140008af5  xor     r8d, r8d; CaseInSensitive
0x140008af8  mov     rdx, rsi; String2
0x140008afb  call    cs:__imp_RtlCompareUnicodeString
0x140008b02  nop     dword ptr [rax+rax+00h]
0x140008b07  test    eax, eax
0x140008b09  jz      short loc_140008B10
0x140008b0b  mov     rbx, [rbx]
0x140008b0e  jmp     short loc_140008AEC
0x140008b10  mov     rcx, [rbx+28h]; Object
0x140008b14  xor     r9d, r9d; Alertable
0x140008b17  xor     r8d, r8d; WaitMode
0x140008b1a  mov     [rsp+58h+Timeout], r15; Timeout
0x140008b1f  xor     edx, edx; WaitReason
0x140008b21  call    cs:__imp_KeWaitForSingleObject
0x140008b28  nop     dword ptr [rax+rax+00h]
0x140008b2d  mov     rdx, [rbx+28h]
0x140008b31  cmp     [rdx+58h], r15
0x140008b35  jz      short loc_140008B71
0x140008b37  cmp     [rdx+60h], rbx
0x140008b3b  jnz     short loc_140008B83
0x140008b3d  inc     dword ptr [rbx+34h]
0x140008b40  xor     edx, edx; Wait
0x140008b42  mov     rcx, [rbx+28h]; Mutex
0x140008b46  call    cs:__imp_KeReleaseMutex
0x140008b4d  nop     dword ptr [rax+rax+00h]
0x140008b52  xor     edx, edx; Wait
0x140008b54  mov     rcx, rdi; Mutex
0x140008b57  call    cs:__imp_KeReleaseMutex
0x140008b5e  nop     dword ptr [rax+rax+00h]
0x140008b63  mov     rax, rbx
0x140008b66  add     rsp, 38h
0x140008b6a  pop     r15
0x140008b6c  pop     rdi
0x140008b6d  pop     rsi
0x140008b6e  pop     rbx
0x140008b6f  retn
0x140008b71  mov     [rdx+58h], rbx
0x140008b75  mov     [rdx+60h], rbx
0x140008b79  jmp     short loc_140008B3D
0x140008b7b  mov     edx, r15d
0x140008b7e  jmp     loc_140008AE2
0x140008b83  mov     rax, [rbx+10h]
0x140008b87  test    rax, rax
0x140008b8a  jz      short loc_140008BA5
0x140008b8c  mov     rcx, [rbx+18h]
0x140008b90  test    rcx, rcx
0x140008b93  jz      short loc_140008BC2
0x140008b95  mov     [rcx+10h], rax
0x140008b99  mov     rcx, [rbx+10h]
0x140008b9d  mov     rax, [rbx+18h]
0x140008ba1  mov     [rcx+18h], rax
0x140008ba5  mov     rax, [rdx+60h]
0x140008ba9  mov     [rax+10h], rbx
0x140008bad  mov     rax, [rdx+60h]
0x140008bb1  mov     [rbx+18h], rax
0x140008bb5  mov     [rbx+10h], r15
0x140008bb9  mov     [rdx+60h], rbx
0x140008bbd  jmp     loc_140008B3D
0x140008bc2  mov     [rdx+58h], rax
0x140008bc6  mov     rax, [rbx+10h]
0x140008bca  mov     [rax+18h], r15
0x140008bce  jmp     short loc_140008BA5
0x140008bd0  mov     [rsp+58h+arg_0], rbp
0x140008bd5  mov     ebp, 0Fh
0x140008bda  mov     [rsp+58h+arg_8], r12
0x140008bdf  lea     r12, WPP_GLOBAL_Control
0x140008be6  mov     [rsp+58h+arg_10], r13
0x140008beb  lea     r13, PowerOf2Primes
0x140008bf2  mov     [rsp+58h+var_28], r14
0x140008bf7  test    ebp, ebp
0x140008bf9  jz      loc_140008C8D
0x140008bff  mov     rcx, cs:WPP_GLOBAL_Control
0x140008c06  cmp     rcx, r12
0x140008c09  jz      short loc_140008C37
0x140008c0b  test    dword ptr [rcx+2Ch], 800h
0x140008c12  jz      short loc_140008C37
0x140008c14  mov     rcx, [rcx+18h]
0x140008c18  lea     r8, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids
0x140008c1f  mov     eax, ebp
0x140008c21  mov     edx, 0Ah
0x140008c26  mov     r9d, ebp
0x140008c29  mov     eax, [r13+rax*4+0]
0x140008c2e  mov     dword ptr [rsp+58h+Timeout], eax
0x140008c32  call    WPP_SF_dd
0x140008c37  mov     eax, ebp
0x140008c39  lea     r14, ds:0[rax*4]
0x140008c41  mov     r8d, [r14+r13]
0x140008c45  cmp     r8d, ebx
0x140008c48  jb      short loc_140008C4E
0x140008c4a  dec     ebp
0x140008c4c  jmp     short loc_140008BF7
0x140008c4e  mov     rcx, cs:WPP_GLOBAL_Control
0x140008c55  cmp     rcx, r12
0x140008c58  jz      short loc_140008C80
0x140008c5a  test    dword ptr [rcx+2Ch], 800h
0x140008c61  jz      short loc_140008C80
0x140008c63  mov     rcx, [rcx+18h]
0x140008c67  mov     edx, 0Bh
0x140008c6c  mov     dword ptr [rsp+58h+Timeout], r8d
0x140008c71  mov     r9d, ebx
0x140008c74  lea     r8, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids
0x140008c7b  call    WPP_SF_dd
0x140008c80  mov     r10d, [r14+r13]
0x140008c84  mov     cs:dword_1400411C4, r10d
0x140008c8b  jmp     short loc_140008C94
0x140008c8d  mov     r10d, cs:dword_1400411C4
0x140008c94  mov     r14, [rsp+58h+var_28]
0x140008c99  mov     r12, [rsp+58h+arg_8]
0x140008c9e  mov     rbp, [rsp+58h+arg_0]
0x140008ca3  mov     r13, [rsp+58h+arg_10]
0x140008ca8  jmp     loc_140008A98
```
