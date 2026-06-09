# FwSvcPorts::Initialize(_tag_FW_PROFILE_TYPE,_tag_FW_RULE * * const,ulong)

- ea: `0x18004b30c`
- end: `0x18004b3a1`
- name: `?Initialize@FwSvcPorts@@AEAAJW4_tag_FW_PROFILE_TYPE@@QEAPEAU_tag_FW_RULE@@K@Z`
- size: `149`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18004b24c`

## callees

- `0x18004b30c`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x18004b368`
- `fwbase!FwReportReturnError` at `0x18004b37d`
- `fwbase!FwReportReturnError` at `0x18004b368`
- `fwbase!FwReportReturnError` at `0x18004b37d`
- `FWPolicyIOMgr!FwCopyRule` at `0x18004b33d`
- `FWPolicyIOMgr!FwCopyRule` at `0x18004b33d`

## pseudocode

```c
__int64 __fastcall FwSvcPorts::Initialize(__int64 a1, int a2, __int64 a3, unsigned int a4)
{
  unsigned int v4; // ebx
  __int64 v5; // rdi
  _QWORD *v6; // rsi
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rdx

  v4 = 0;
  *(_DWORD *)(a1 + 24) = a2;
  v5 = 0;
  v6 = (_QWORD *)(a1 + 32);
  while ( (unsigned int)v5 < a4 )
  {
    v10 = *(_QWORD *)(a3 + 8 * v5);
    if ( !v10 )
    {
      v4 = -2147418113;
      v12 = 2147549183LL;
      goto LABEL_8;
    }
    v11 = FwCopyRule(v10, v6);
    v4 = v11;
    if ( v11 < 0 )
    {
      v12 = (unsigned int)v11;
LABEL_8:
      FwReportReturnError("FwSvcPorts::Initialize", v12);
      return (unsigned int)FwReportReturnError("FwSvcPorts::Initialize", v4);
    }
    v6 = (_QWORD *)*v6;
    v5 = (unsigned int)(v5 + 1);
  }
  *(_DWORD *)(a1 + 40) = a4;
  return v4;
}

```

## disassembly

```asm
0x18004b30c  push    rbx
0x18004b30e  push    rbp
0x18004b30f  push    rsi
0x18004b310  push    rdi
0x18004b311  push    r14
0x18004b313  push    r15
0x18004b315  sub     rsp, 28h
0x18004b319  xor     ebx, ebx
0x18004b31b  mov     [rcx+18h], edx
0x18004b31e  xor     edi, edi
0x18004b320  lea     rsi, [rcx+20h]
0x18004b324  mov     ebp, r9d
0x18004b327  mov     r15, r8
0x18004b32a  mov     r14, rcx
0x18004b32d  cmp     edi, ebp
0x18004b32f  jnb     short loc_18004B38D
0x18004b331  mov     rcx, [r15+rdi*8]
0x18004b335  test    rcx, rcx
0x18004b338  jz      short loc_18004B35A
0x18004b33a  mov     rdx, rsi
0x18004b33d  call    cs:__imp_FwCopyRule
0x18004b344  nop     dword ptr [rax+rax+00h]
0x18004b349  mov     ebx, eax
0x18004b34b  test    eax, eax
0x18004b34d  js      short loc_18004B356
0x18004b34f  mov     rsi, [rsi]
0x18004b352  inc     edi
0x18004b354  jmp     short loc_18004B32D
0x18004b356  mov     edx, eax
0x18004b358  jmp     short loc_18004B361
0x18004b35a  mov     ebx, 8000FFFFh
0x18004b35f  mov     edx, ebx
0x18004b361  lea     rcx, aFwsvcportsInit; "FwSvcPorts::Initialize"
0x18004b368  call    cs:__imp_FwReportReturnError
0x18004b36f  nop     dword ptr [rax+rax+00h]
0x18004b374  mov     edx, ebx
0x18004b376  lea     rcx, aFwsvcportsInit; "FwSvcPorts::Initialize"
0x18004b37d  call    cs:__imp_FwReportReturnError
0x18004b384  nop     dword ptr [rax+rax+00h]
0x18004b389  mov     ebx, eax
0x18004b38b  jmp     short loc_18004B391
0x18004b38d  mov     [r14+28h], ebp
0x18004b391  mov     eax, ebx
0x18004b393  add     rsp, 28h
0x18004b397  pop     r15
0x18004b399  pop     r14
0x18004b39b  pop     rdi
0x18004b39c  pop     rsi
0x18004b39d  pop     rbp
0x18004b39e  pop     rbx
0x18004b39f  retn
```
