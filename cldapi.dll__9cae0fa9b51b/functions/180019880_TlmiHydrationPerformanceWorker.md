# TlmiHydrationPerformanceWorker

- ea: `0x180019880`
- end: `0x180019a65`
- name: `TlmiHydrationPerformanceWorker`
- size: `485`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180001078`
- `0x180001aa0`
- `0x180019880`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001991a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001991a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180019967`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180019967`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18001997b`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18001997b`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18001998c`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18001998c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800198dc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800198fc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800198dc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800198fc`

## pseudocode

```c
__int64 __fastcall TlmiHydrationPerformanceWorker(PVOID Parameter)
{
  struct _RTL_AVL_TABLE *v1; // rbx
  int v2; // edi
  struct _RTL_AVL_TABLE *v3; // rax
  PVOID v4; // rax
  int v6; // [rsp+30h] [rbp-68h] BYREF
  __int64 v7; // [rsp+38h] [rbp-60h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+40h] [rbp-58h] BYREF
  int *v9; // [rsp+60h] [rbp-38h]
  __int64 v10; // [rsp+68h] [rbp-30h]
  __int64 *v11; // [rsp+70h] [rbp-28h]
  __int64 v12; // [rsp+78h] [rbp-20h]

  while ( byte_18002A930
       && !NtCurrentPeb()->Ldr->ShutdownInProgress
       && !WaitForSingleObject(hEvent, 0xFFFFFFFF)
       && WaitForSingleObject(qword_18002AB50, 0x36EE80u) == 258 )
  {
    RtlAcquireSRWLockExclusive(&qword_18002AA60);
    v1 = qword_18002AA68;
    v2 = dword_18002AB40;
    dword_18002AB40 = 0;
    v3 = &stru_18002AAD8;
    if ( qword_18002AA68 != &stru_18002AA70 )
      v3 = &stru_18002AA70;
    qword_18002AA68 = v3;
    RtlReleaseSRWLockExclusive(&qword_18002AA60);
    while ( 1 )
    {
      v4 = RtlEnumerateGenericTableAvl(v1, 1u);
      if ( !v4 )
        break;
      RtlDeleteElementGenericTableAvl(v1, v4);
    }
    if ( v2
      && (unsigned int)dword_18002A1A0 > 5
      && (qword_18002A1B0 & 0x400000000000LL) != 0
      && (qword_18002A1B8 & 0x400000000000LL) == qword_18002A1B8 )
    {
      v6 = v2;
      v9 = &v6;
      v10 = 4;
      v11 = &v7;
      v7 = 0x1000000;
      v12 = 8;
      tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18002A1A0, (unsigned __int8 *)word_18002477A, 0, 0, 4u, &v8);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180019880  mov     [rsp+arg_0], rbx
0x180019885  mov     [rsp+arg_8], rbp
0x18001988a  push    rdi
0x18001988b  sub     rsp, 90h
0x180019892  mov     rax, cs:__security_cookie
0x180019899  xor     rax, rsp
0x18001989c  mov     [rsp+98h+var_18], rax
0x1800198a4  mov     rbp, 400000000000h
0x1800198ae  cmp     cs:byte_18002A930, 0
0x1800198b5  jz      loc_180019A3D
0x1800198bb  mov     rax, gs:60h
0x1800198c4  mov     rcx, [rax+18h]
0x1800198c8  cmp     byte ptr [rcx+48h], 0
0x1800198cc  jnz     loc_180019A3D
0x1800198d2  mov     rcx, cs:hEvent; hHandle
0x1800198d9  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800198dc  call    cs:__imp_WaitForSingleObject
0x1800198e3  nop     dword ptr [rax+rax+00h]
0x1800198e8  test    eax, eax
0x1800198ea  jnz     loc_180019A3D
0x1800198f0  mov     rcx, cs:qword_18002AB50; hHandle
0x1800198f7  mov     edx, 36EE80h; dwMilliseconds
0x1800198fc  call    cs:__imp_WaitForSingleObject
0x180019903  nop     dword ptr [rax+rax+00h]
0x180019908  cmp     eax, 102h
0x18001990d  jnz     loc_180019A3D
0x180019913  lea     rcx, qword_18002AA60
0x18001991a  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180019921  nop     dword ptr [rax+rax+00h]
0x180019926  mov     rbx, cs:qword_18002AA68
0x18001992d  lea     rcx, stru_18002AA70
0x180019934  mov     edi, cs:dword_18002AB40
0x18001993a  lea     rdx, stru_18002AA70
0x180019941  cmp     rbx, rcx
0x180019944  mov     cs:dword_18002AB40, 0
0x18001994e  lea     rax, stru_18002AAD8
0x180019955  cmovnz  rax, rdx
0x180019959  lea     rcx, qword_18002AA60
0x180019960  mov     cs:qword_18002AA68, rax
0x180019967  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001996e  nop     dword ptr [rax+rax+00h]
0x180019973  jmp     short loc_180019987
0x180019975  mov     rdx, rax; Buffer
0x180019978  mov     rcx, rbx; Table
0x18001997b  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180019982  nop     dword ptr [rax+rax+00h]
0x180019987  mov     dl, 1; Restart
0x180019989  mov     rcx, rbx; Table
0x18001998c  call    cs:__imp_RtlEnumerateGenericTableAvl
0x180019993  nop     dword ptr [rax+rax+00h]
0x180019998  test    rax, rax
0x18001999b  jnz     short loc_180019975
0x18001999d  test    edi, edi
0x18001999f  jz      loc_1800198AE
0x1800199a5  mov     eax, cs:dword_18002A1A0
0x1800199ab  cmp     eax, 5
0x1800199ae  jbe     loc_1800198AE
0x1800199b4  mov     rcx, cs:qword_18002A1B8
0x1800199bb  mov     rax, cs:qword_18002A1B0
0x1800199c2  test    rbp, rax
0x1800199c5  jz      loc_1800198AE
0x1800199cb  mov     rax, rcx
0x1800199ce  and     rax, rbp
0x1800199d1  cmp     rax, rcx
0x1800199d4  jnz     loc_1800198AE
0x1800199da  lea     rax, [rsp+98h+var_68]
0x1800199df  mov     [rsp+98h+var_68], edi
0x1800199e3  mov     [rsp+98h+var_38], rax
0x1800199e8  lea     rdx, word_18002477A
0x1800199ef  lea     rax, [rsp+98h+var_60]
0x1800199f4  mov     [rsp+98h+var_30], 4
0x1800199fd  mov     [rsp+98h+var_28], rax
0x180019a02  lea     rcx, dword_18002A1A0
0x180019a09  lea     rax, [rsp+98h+var_58]
0x180019a0e  mov     [rsp+98h+var_60], 1000000h
0x180019a17  mov     [rsp+98h+var_70], rax
0x180019a1c  xor     r9d, r9d
0x180019a1f  xor     r8d, r8d
0x180019a22  mov     [rsp+98h+var_78], 4
0x180019a2a  mov     [rsp+98h+var_20], 8
0x180019a33  call    _tlgWriteTransfer_EventWriteTransfer
0x180019a38  jmp     loc_1800198AE
0x180019a3d  xor     eax, eax
0x180019a3f  mov     rcx, [rsp+98h+var_18]
0x180019a47  xor     rcx, rsp; StackCookie
0x180019a4a  call    __security_check_cookie
0x180019a4f  lea     r11, [rsp+98h+var_8]
0x180019a57  mov     rbx, [r11+10h]
0x180019a5b  mov     rbp, [r11+18h]
0x180019a5f  mov     rsp, r11
0x180019a62  pop     rdi
0x180019a63  retn
```
