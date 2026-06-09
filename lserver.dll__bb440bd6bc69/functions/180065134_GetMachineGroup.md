# GetMachineGroup

- ea: `0x180065134`
- end: `0x180065277`
- name: `GetMachineGroup`
- size: `323`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180020cb4`

## callees

- `0x18001ec04`
- `0x180065134`

## import_xrefs

- `ADVAPI32!LsaOpenPolicy` at `0x180065181`
- `ADVAPI32!LsaOpenPolicy` at `0x180065181`
- `ADVAPI32!LsaFreeMemory` at `0x18006521e`
- `ADVAPI32!LsaFreeMemory` at `0x18006521e`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x1800651c1`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x1800651c1`
- `ADVAPI32!LsaNtStatusToWinError` at `0x180065193`
- `ADVAPI32!LsaNtStatusToWinError` at `0x18006524a`
- `ADVAPI32!LsaNtStatusToWinError` at `0x180065193`
- `ADVAPI32!LsaNtStatusToWinError` at `0x18006524a`
- `ADVAPI32!LsaClose` at `0x180065234`
- `ADVAPI32!LsaClose` at `0x180065234`
- `KERNEL32!LocalAlloc` at `0x1800651e1`
- `KERNEL32!LocalAlloc` at `0x1800651e1`
- `KERNEL32!SetLastError` at `0x1800651a1`
- `KERNEL32!SetLastError` at `0x180065258`
- `KERNEL32!SetLastError` at `0x1800651a1`
- `KERNEL32!SetLastError` at `0x180065258`

## pseudocode

```c
__int64 __fastcall GetMachineGroup(__int64 a1, unsigned __int16 **a2)
{
  unsigned int v2; // ebx
  NTSTATUS v4; // eax
  DWORD v5; // eax
  NTSTATUS v7; // edi
  unsigned __int16 *v8; // rax
  DWORD v9; // eax
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  PVOID Buffer; // [rsp+80h] [rbp+20h] BYREF
  PVOID PolicyHandle; // [rsp+90h] [rbp+30h] BYREF

  v2 = 0;
  Buffer = 0;
  PolicyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v4 = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
  if ( v4 )
  {
    v5 = LsaNtStatusToWinError(v4);
    SetLastError(v5);
    return 0;
  }
  else
  {
    v7 = LsaQueryInformationPolicy(PolicyHandle, PolicyPrimaryDomainInformation, &Buffer);
    if ( !v7 )
    {
      v8 = (unsigned __int16 *)LocalAlloc(0x40u, *(unsigned __int16 *)Buffer + 2LL);
      *a2 = v8;
      if ( v8 )
      {
        StringCchCopyNW(
          v8,
          ((unsigned __int64)*(unsigned __int16 *)Buffer >> 1) + 1,
          *((const unsigned __int16 **)Buffer + 1),
          ((unsigned __int64)*(unsigned __int16 *)Buffer >> 1) + 1);
        v2 = 1;
      }
    }
    if ( Buffer )
      LsaFreeMemory(Buffer);
    if ( PolicyHandle != (PVOID)-1LL )
      LsaClose(PolicyHandle);
    if ( !v2 )
    {
      if ( v7 )
      {
        v9 = LsaNtStatusToWinError(v7);
        SetLastError(v9);
      }
    }
    return v2;
  }
}

```

## disassembly

```asm
0x180065134  mov     [rsp-18h+arg_8], rbx
0x180065139  mov     [rsp-18h+Buffer], rcx
0x18006513e  push    rbp
0x18006513f  push    rsi
0x180065140  push    rdi
0x180065141  mov     rbp, rsp
0x180065144  sub     rsp, 60h
0x180065148  xorps   xmm0, xmm0
0x18006514b  lea     rdi, [rbp+ObjectAttributes]
0x18006514f  xor     ebx, ebx
0x180065151  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x180065155  and     [rbp+Buffer], rbx
0x180065159  xor     eax, eax
0x18006515b  and     [rbp+PolicyHandle], rax
0x18006515f  mov     rsi, rdx
0x180065162  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180065166  lea     ecx, [rbx+30h]
0x180065169  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18006516d  lea     r8d, [rbx+1]; DesiredAccess
0x180065171  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180065175  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x180065179  rep stosb
0x18006517b  xor     ecx, ecx; SystemName
0x18006517d  movups  [rbp+var_40], xmm0
0x180065181  call    cs:__imp_LsaOpenPolicy
0x180065188  nop     dword ptr [rax+rax+00h]
0x18006518d  test    eax, eax
0x18006518f  jz      short loc_1800651B4
0x180065191  mov     ecx, eax; Status
0x180065193  call    cs:__imp_LsaNtStatusToWinError
0x18006519a  nop     dword ptr [rax+rax+00h]
0x18006519f  mov     ecx, eax; dwErrCode
0x1800651a1  call    cs:__imp_SetLastError
0x1800651a8  nop     dword ptr [rax+rax+00h]
0x1800651ad  xor     eax, eax
0x1800651af  jmp     loc_180065266
0x1800651b4  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x1800651b8  lea     r8, [rbp+Buffer]; Buffer
0x1800651bc  mov     edx, 3; InformationClass
0x1800651c1  call    cs:__imp_LsaQueryInformationPolicy
0x1800651c8  nop     dword ptr [rax+rax+00h]
0x1800651cd  mov     edi, eax
0x1800651cf  test    eax, eax
0x1800651d1  jnz     short loc_180065215
0x1800651d3  mov     rax, [rbp+Buffer]
0x1800651d7  lea     ecx, [rdi+40h]; uFlags
0x1800651da  movzx   edx, word ptr [rax]
0x1800651dd  add     rdx, 2; uBytes
0x1800651e1  call    cs:__imp_LocalAlloc
0x1800651e8  nop     dword ptr [rax+rax+00h]
0x1800651ed  mov     [rsi], rax
0x1800651f0  mov     rcx, rax; unsigned __int16 *
0x1800651f3  test    rax, rax
0x1800651f6  jz      short loc_180065215
0x1800651f8  mov     r8, [rbp+Buffer]
0x1800651fc  movzx   edx, word ptr [r8]
0x180065200  mov     r8, [r8+8]; unsigned __int16 *
0x180065204  shr     rdx, 1
0x180065207  inc     rdx; unsigned __int64
0x18006520a  mov     r9, rdx; unsigned __int64
0x18006520d  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180065212  lea     ebx, [rdi+1]
0x180065215  mov     rcx, [rbp+Buffer]; Buffer
0x180065219  test    rcx, rcx
0x18006521c  jz      short loc_18006522A
0x18006521e  call    cs:__imp_LsaFreeMemory
0x180065225  nop     dword ptr [rax+rax+00h]
0x18006522a  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x18006522e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180065232  jz      short loc_180065240
0x180065234  call    cs:__imp_LsaClose
0x18006523b  nop     dword ptr [rax+rax+00h]
0x180065240  test    ebx, ebx
0x180065242  jnz     short loc_180065264
0x180065244  test    edi, edi
0x180065246  jz      short loc_180065264
0x180065248  mov     ecx, edi; Status
0x18006524a  call    cs:__imp_LsaNtStatusToWinError
0x180065251  nop     dword ptr [rax+rax+00h]
0x180065256  mov     ecx, eax; dwErrCode
0x180065258  call    cs:__imp_SetLastError
0x18006525f  nop     dword ptr [rax+rax+00h]
0x180065264  mov     eax, ebx
0x180065266  mov     rbx, [rsp+60h+arg_8]
0x18006526e  add     rsp, 60h
0x180065272  pop     rdi
0x180065273  pop     rsi
0x180065274  pop     rbp
0x180065275  retn
```
