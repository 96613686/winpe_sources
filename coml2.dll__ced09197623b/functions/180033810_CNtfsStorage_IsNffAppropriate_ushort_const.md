# CNtfsStorage::IsNffAppropriate(ushort const *)

- ea: `0x180033810`
- end: `0x1800338d4`
- name: `?IsNffAppropriate@CNtfsStorage@@SAJPEBG@Z`
- size: `196`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, loader_planting`

## callers

- `0x180033544`
- `0x180039a04`

## callees

- `0x180033810`
- `0x1800338dc`
- `0x180034068`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800338cc`
- `ntdll!RtlFreeHeap` at `0x1800338cc`
- `ntdll!NtClose` at `0x1800338af`
- `ntdll!NtClose` at `0x1800338af`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18003384d`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18003384d`

## pseudocode

```c
__int64 __fastcall CNtfsStorage::IsNffAppropriate(const unsigned __int16 *a1)
{
  int IsNffAppropriate; // ebx
  PWSTR Buffer; // rsi
  const unsigned __int16 *v4; // rdx
  __int64 v5; // r8
  int v6; // r9d
  struct _UNICODE_STRING NtPathName; // [rsp+40h] [rbp-18h] BYREF
  HANDLE Handle; // [rsp+60h] [rbp+8h] BYREF

  Handle = (HANDLE)-1LL;
  NtPathName = 0;
  if ( a1 && RtlDosPathNameToNtPathName_U(a1, &NtPathName, 0, 0) )
  {
    Buffer = NtPathName.Buffer;
    IsNffAppropriate = CNtfsStorage::OpenNtFileHandle(&NtPathName, 0, 0, 64, 0, 0, &Handle);
    if ( IsNffAppropriate >= 0 )
      IsNffAppropriate = CNtfsStorage::IsNffAppropriate(Handle, v4, v5, v6);
    if ( Buffer )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
    if ( Handle != (HANDLE)-1LL )
      NtClose(Handle);
  }
  else
  {
    return (unsigned int)-2147286788;
  }
  return (unsigned int)IsNffAppropriate;
}

```

## disassembly

```asm
0x180033810  mov     [rsp+arg_8], rbx
0x180033815  push    rsi
0x180033816  sub     rsp, 50h
0x18003381a  mov     [rsp+58h+Handle], 0FFFFFFFFFFFFFFFFh
0x180033823  xorps   xmm0, xmm0
0x180033826  movups  xmmword ptr [rsp+58h+NtPathName.Length], xmm0
0x18003382b  test    rcx, rcx
0x18003382e  jnz     short loc_180033842
0x180033830  mov     ebx, 800300FCh
0x180033835  mov     eax, ebx
0x180033837  mov     rbx, [rsp+58h+arg_8]
0x18003383c  add     rsp, 50h
0x180033840  pop     rsi
0x180033841  retn
0x180033842  xor     r9d, r9d; DirectoryInfo
0x180033845  lea     rdx, [rsp+58h+NtPathName]; NtPathName
0x18003384a  xor     r8d, r8d; NtFileNamePart
0x18003384d  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180033853  test    al, al
0x180033855  jz      short loc_180033830
0x180033857  mov     rsi, [rsp+58h+NtPathName.Buffer]
0x18003385c  lea     rax, [rsp+58h+Handle]
0x180033861  mov     [rsp+58h+var_28], rax; void **
0x180033866  lea     rcx, [rsp+58h+NtPathName]; struct _UNICODE_STRING *
0x18003386b  mov     [rsp+58h+var_30], 0; int
0x180033873  mov     r9d, 40h ; '@'; unsigned int
0x180033879  xor     r8d, r8d; void *
0x18003387c  mov     [rsp+58h+var_38], 0; unsigned int
0x180033884  xor     edx, edx; void *
0x180033886  call    ?OpenNtFileHandle@CNtfsStorage@@CAJAEBU_UNICODE_STRING@@PEAX1KKHPEAPEAX@Z; CNtfsStorage::OpenNtFileHandle(_UNICODE_STRING const &,void *,void *,ulong,ulong,int,void * *)
0x18003388b  mov     ebx, eax
0x18003388d  test    eax, eax
0x18003388f  js      short loc_18003389D
0x180033891  mov     rcx, [rsp+58h+Handle]; void *
0x180033896  call    ?IsNffAppropriate@CNtfsStorage@@KAJPEAXPEBG@Z; CNtfsStorage::IsNffAppropriate(void *,ushort const *)
0x18003389b  mov     ebx, eax
0x18003389d  test    rsi, rsi
0x1800338a0  jnz     short loc_1800338BA
0x1800338a2  cmp     [rsp+58h+Handle], 0FFFFFFFFFFFFFFFFh
0x1800338a8  jz      short loc_180033835
0x1800338aa  mov     rcx, [rsp+58h+Handle]; Handle
0x1800338af  call    cs:__imp_NtClose
0x1800338b5  jmp     loc_180033835
0x1800338ba  mov     rcx, gs:60h
0x1800338c3  mov     r8, rsi; P
0x1800338c6  xor     edx, edx; Flags
0x1800338c8  mov     rcx, [rcx+30h]; HeapHandle
0x1800338cc  call    cs:__imp_RtlFreeHeap
0x1800338d2  jmp     short loc_1800338A2
```
