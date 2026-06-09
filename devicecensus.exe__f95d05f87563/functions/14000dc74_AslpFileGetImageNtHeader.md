# AslpFileGetImageNtHeader

- ea: `0x14000dc74`
- end: `0x14000dd37`
- name: `AslpFileGetImageNtHeader`
- size: `195`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `9`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x14000c110`
- `0x14000cfe8`
- `0x14000d420`
- `0x14000dd40`
- `0x14000df84`
- `0x14000eab4`
- `0x14000f1f4`
- `0x14000f7ac`
- `0x1400101cc`

## callees

- `0x140007074`
- `0x14000dc74`

## string_xrefs

- `0x14000dc99`: `AslpFileGetImageNtHeader`
- `0x14000dcf3`: `AslpFileGetImageNtHeader`
- `0x14000dd1d`: `AslpFileGetImageNtHeader`

## pseudocode

```c
__int64 __fastcall AslpFileGetImageNtHeader(_QWORD *a1, __int64 a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rcx
  __int64 v5; // r8

  if ( *(_DWORD *)(a2 + 56) == 6 )
  {
    v4 = *(_QWORD *)(a2 + 32);
    v5 = *(int *)(v4 + 60);
    if ( *(_QWORD *)(a2 + 24) < (unsigned __int64)(v5 + 264) || *(_QWORD *)(a2 + 40) < (unsigned __int64)(v5 + 264) )
    {
      v3 = -1073741701;
      AslLogCallPrintf(1, "AslpFileGetImageNtHeader", 3777, "File mapping invalid [%x]", -1073741701);
    }
    else
    {
      *a1 = v5 + v4;
      return 0;
    }
  }
  else
  {
    v3 = -1073741637;
    AslLogCallPrintf(1, "AslpFileGetImageNtHeader", 3758, "File mapping not a PE [%x]", -1073741637);
  }
  return v3;
}

```

## disassembly

```asm
0x14000dc74  push    rbx
0x14000dc76  sub     rsp, 40h
0x14000dc7a  mov     r9, rcx
0x14000dc7d  cmp     dword ptr [rdx+38h], 6
0x14000dc81  jz      short loc_14000DCAF
0x14000dc83  mov     ebx, 0C00000BBh
0x14000dc88  mov     [rsp+48h+var_28], ebx
0x14000dc8c  lea     r9, aFileMappingNot; "File mapping not a PE [%x]"
0x14000dc93  mov     r8d, 0EAEh
0x14000dc99  lea     rdx, aAslpfilegetima_3; "AslpFileGetImageNtHeader"
0x14000dca0  mov     ecx, 1
0x14000dca5  call    AslLogCallPrintf
0x14000dcaa  jmp     loc_14000DD2F
0x14000dcaf  mov     rcx, [rdx+20h]
0x14000dcb3  movsxd  r8, dword ptr [rcx+3Ch]
0x14000dcb7  lea     rax, [r8+108h]
0x14000dcbe  cmp     [rdx+18h], rax
0x14000dcc2  jb      short loc_14000DCD9
0x14000dcc4  cmp     [rdx+28h], rax
0x14000dcc8  jb      short loc_14000DCD9
0x14000dcca  lea     rax, [r8+rcx]
0x14000dcce  mov     [r9], rax
0x14000dcd1  xor     ebx, ebx
0x14000dcd3  mov     [rsp+48h+var_18], ebx
0x14000dcd7  jmp     short loc_14000DD04
0x14000dcd9  mov     ebx, 0C000007Bh
0x14000dcde  mov     [rsp+48h+var_18], ebx
0x14000dce2  mov     [rsp+48h+var_28], ebx
0x14000dce6  lea     r9, aFileMappingInv; "File mapping invalid [%x]"
0x14000dced  mov     r8d, 0EC1h
0x14000dcf3  lea     rdx, aAslpfilegetima_3; "AslpFileGetImageNtHeader"
0x14000dcfa  mov     ecx, 1
0x14000dcff  call    AslLogCallPrintf
0x14000dd04  jmp     short loc_14000DD2F
0x14000dd06  mov     ebx, eax
0x14000dd08  mov     [rsp+48h+var_18], eax
0x14000dd0c  mov     [rsp+48h+var_28], eax
0x14000dd10  lea     r9, aExceptionEncou; "Exception encountered [%x]"
0x14000dd17  mov     r8d, 0ECAh
0x14000dd1d  lea     rdx, aAslpfilegetima_3; "AslpFileGetImageNtHeader"
0x14000dd24  mov     ecx, 1
0x14000dd29  call    AslLogCallPrintf
0x14000dd2e  nop
0x14000dd2f  mov     eax, ebx
0x14000dd31  add     rsp, 40h
0x14000dd35  pop     rbx
0x14000dd36  retn
0x140011836  push    rbp
0x140011838  sub     rsp, 30h
0x14001183c  mov     rbp, rdx
0x14001183f  mov     rax, [rcx]
0x140011842  xor     ecx, ecx
0x140011844  cmp     dword ptr [rax], 0C00000FDh
0x14001184a  setnz   cl
0x14001184d  mov     [rbp+34h], ecx
0x140011850  mov     eax, [rbp+34h]
0x140011853  add     rsp, 30h
0x140011857  pop     rbp
0x140011858  retn
```
