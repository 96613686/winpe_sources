# BiGetCurrentBcdMutantHandle

- ea: `0x18002ddcc`
- end: `0x18002dea1`
- name: `BiGetCurrentBcdMutantHandle`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002d940`

## callees

- `0x18002ddcc`

## import_xrefs

- `ntdll!ZwClose` at `0x18002de7d`
- `ntdll!ZwClose` at `0x18002de7d`
- `ntdll!ZwOpenMutant` at `0x18002de36`
- `ntdll!ZwOpenMutant` at `0x18002de36`

## pseudocode

```c
NTSTATUS __fastcall BiGetCurrentBcdMutantHandle(_QWORD *a1)
{
  NTSTATUS result; // eax
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-30h] BYREF
  void *MutantHandle; // [rsp+68h] [rbp+18h] BYREF

  MutantHandle = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  if ( BcdMutantHandle )
  {
    *a1 = BcdMutantHandle;
  }
  else
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)L"8:";
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    result = ZwOpenMutant(&MutantHandle, 0x100000u, &ObjectAttributes);
    if ( result == -1073741772 )
    {
      _InterlockedCompareExchange64((volatile signed __int64 *)&BcdMutantHandle, -1, 0);
      *a1 = BcdMutantHandle;
    }
    else
    {
      if ( result < 0 )
        return result;
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)&BcdMutantHandle, (signed __int64)MutantHandle, 0) )
        ZwClose(MutantHandle);
      *a1 = BcdMutantHandle;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002ddcc  mov     [rsp-8+arg_0], rbx
0x18002ddd1  push    rbp
0x18002ddd2  mov     rbp, rsp
0x18002ddd5  sub     rsp, 50h
0x18002ddd9  xor     eax, eax
0x18002dddb  mov     [rbp+MutantHandle], 0
0x18002dde3  mov     dword ptr [rbp+ObjectAttributes+4], eax
0x18002dde6  mov     rbx, rcx
0x18002dde9  mov     dword ptr [rbp+ObjectAttributes+1Ch], eax
0x18002ddec  mov     rax, cs:BcdMutantHandle
0x18002ddf3  test    rax, rax
0x18002ddf6  jz      short loc_18002DE00
0x18002ddf8  mov     [rcx], rax
0x18002ddfb  jmp     loc_18002DE93
0x18002de00  lea     rax, BcdSyncMutantName; "8:"
0x18002de07  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18002de0e  xorps   xmm0, xmm0
0x18002de11  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18002de15  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18002de19  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18002de21  mov     edx, 100000h; DesiredAccess
0x18002de26  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18002de2d  lea     rcx, [rbp+MutantHandle]; MutantHandle
0x18002de31  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18002de36  call    cs:__imp_ZwOpenMutant
0x18002de3d  nop     dword ptr [rax+rax+00h]
0x18002de42  cmp     eax, 0C0000034h
0x18002de47  jnz     short loc_18002DE64
0x18002de49  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002de4d  xor     eax, eax
0x18002de4f  lock cmpxchg cs:BcdMutantHandle, rcx
0x18002de58  mov     rcx, cs:BcdMutantHandle
0x18002de5f  mov     [rbx], rcx
0x18002de62  jmp     short loc_18002DE93
0x18002de64  test    eax, eax
0x18002de66  js      short loc_18002DE95
0x18002de68  mov     rcx, [rbp+MutantHandle]
0x18002de6c  xor     eax, eax
0x18002de6e  lock cmpxchg cs:BcdMutantHandle, rcx
0x18002de77  jz      short loc_18002DE89
0x18002de79  mov     rcx, [rbp+MutantHandle]; Handle
0x18002de7d  call    cs:__imp_ZwClose
0x18002de84  nop     dword ptr [rax+rax+00h]
0x18002de89  mov     rax, cs:BcdMutantHandle
0x18002de90  mov     [rbx], rax
0x18002de93  xor     eax, eax
0x18002de95  mov     rbx, [rsp+50h+arg_0]
0x18002de9a  add     rsp, 50h
0x18002de9e  pop     rbp
0x18002de9f  retn
```
