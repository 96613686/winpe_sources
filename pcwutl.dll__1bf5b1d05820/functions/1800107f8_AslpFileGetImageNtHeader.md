# AslpFileGetImageNtHeader

- ea: `0x1800107f8`
- end: `0x1800108bb`
- name: `AslpFileGetImageNtHeader`
- size: `195`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000e01c`
- `0x18000fb6c`
- `0x18000ffa4`
- `0x1800108c4`
- `0x180010b08`
- `0x180011638`
- `0x180011d78`
- `0x180012c38`
- `0x180013658`

## callees

- `0x18000e240`
- `0x1800107f8`

## string_xrefs

- `0x18001081d`: `AslpFileGetImageNtHeader`
- `0x180010877`: `AslpFileGetImageNtHeader`
- `0x1800108a1`: `AslpFileGetImageNtHeader`

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
0x1800107f8  push    rbx
0x1800107fa  sub     rsp, 40h
0x1800107fe  mov     r9, rcx
0x180010801  cmp     dword ptr [rdx+38h], 6
0x180010805  jz      short loc_180010833
0x180010807  mov     ebx, 0C00000BBh
0x18001080c  mov     [rsp+48h+var_28], ebx
0x180010810  lea     r9, aFileMappingNot; "File mapping not a PE [%x]"
0x180010817  mov     r8d, 0EAEh
0x18001081d  lea     rdx, aAslpfilegetima_3; "AslpFileGetImageNtHeader"
0x180010824  mov     ecx, 1
0x180010829  call    AslLogCallPrintf
0x18001082e  jmp     loc_1800108B3
0x180010833  mov     rcx, [rdx+20h]
0x180010837  movsxd  r8, dword ptr [rcx+3Ch]
0x18001083b  lea     rax, [r8+108h]
0x180010842  cmp     [rdx+18h], rax
0x180010846  jb      short loc_18001085D
0x180010848  cmp     [rdx+28h], rax
0x18001084c  jb      short loc_18001085D
0x18001084e  lea     rax, [r8+rcx]
0x180010852  mov     [r9], rax
0x180010855  xor     ebx, ebx
0x180010857  mov     [rsp+48h+var_18], ebx
0x18001085b  jmp     short loc_180010888
0x18001085d  mov     ebx, 0C000007Bh
0x180010862  mov     [rsp+48h+var_18], ebx
0x180010866  mov     [rsp+48h+var_28], ebx
0x18001086a  lea     r9, aFileMappingInv; "File mapping invalid [%x]"
0x180010871  mov     r8d, 0EC1h
0x180010877  lea     rdx, aAslpfilegetima_3; "AslpFileGetImageNtHeader"
0x18001087e  mov     ecx, 1
0x180010883  call    AslLogCallPrintf
0x180010888  jmp     short loc_1800108B3
0x18001088a  mov     ebx, eax
0x18001088c  mov     [rsp+48h+var_18], eax
0x180010890  mov     [rsp+48h+var_28], eax
0x180010894  lea     r9, aExceptionEncou; "Exception encountered [%x]"
0x18001089b  mov     r8d, 0ECAh
0x1800108a1  lea     rdx, aAslpfilegetima_3; "AslpFileGetImageNtHeader"
0x1800108a8  mov     ecx, 1
0x1800108ad  call    AslLogCallPrintf
0x1800108b2  nop
0x1800108b3  mov     eax, ebx
0x1800108b5  add     rsp, 40h
0x1800108b9  pop     rbx
0x1800108ba  retn
0x180019716  push    rbp
0x180019718  sub     rsp, 30h
0x18001971c  mov     rbp, rdx
0x18001971f  mov     rax, [rcx]
0x180019722  xor     ecx, ecx
0x180019724  cmp     dword ptr [rax], 0C00000FDh
0x18001972a  setnz   cl
0x18001972d  mov     [rbp+34h], ecx
0x180019730  mov     eax, [rbp+34h]
0x180019733  add     rsp, 30h
0x180019737  pop     rbp
0x180019738  retn
```
