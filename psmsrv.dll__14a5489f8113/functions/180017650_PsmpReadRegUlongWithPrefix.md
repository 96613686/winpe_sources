# PsmpReadRegUlongWithPrefix

- ea: `0x180017650`
- end: `0x18001775f`
- name: `PsmpReadRegUlongWithPrefix`
- size: `271`
- prototype: `NTSTATUS __fastcall(HANDLE KeyHandle, STRSAFE_PCNZWCH pszSrc, size_t *SourceString, _DWORD *)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001752c`
- `0x1800209f4`
- `0x180020f3c`

## callees

- `0x180017650`
- `0x180017980`
- `0x18001b7e0`
- `0x18001ea3c`
- `0x180022570`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800176c8`
- `ntdll!RtlInitUnicodeString` at `0x1800176c8`
- `ntdll!NtQueryValueKey` at `0x1800176f3`
- `ntdll!NtQueryValueKey` at `0x1800176f3`

## pseudocode

```c
NTSTATUS __fastcall PsmpReadRegUlongWithPrefix(
        HANDLE KeyHandle,
        STRSAFE_PCNZWCH pszSrc,
        size_t *SourceString,
        _DWORD *a4)
{
  size_t v6; // rdx
  STRSAFE_LPCWSTR v7; // r11
  wchar_t *v8; // rdx
  NTSTATUS result; // eax
  size_t Length; // [rsp+20h] [rbp-E0h]
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-C8h] BYREF
  __int128 KeyValueInformation; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t pszDest[264]; // [rsp+60h] [rbp-A0h] BYREF

  ResultLength = 0;
  DestinationString = 0;
  KeyValueInformation = 0;
  if ( pszSrc )
  {
    StringCopyWorkerW_0(pszDest, 0x104u, SourceString, pszSrc, Length);
    StringCchCatW(pszDest, v6, v7);
    v8 = pszDest;
  }
  else
  {
    v8 = (wchar_t *)SourceString;
  }
  RtlInitUnicodeString(&DestinationString, v8);
  result = NtQueryValueKey(
             KeyHandle,
             &DestinationString,
             KeyValuePartialInformation,
             &KeyValueInformation,
             0x10u,
             &ResultLength);
  if ( result >= 0 )
  {
    if ( *(_QWORD *)((char *)&KeyValueInformation + 4) == 0x400000004LL )
    {
      *a4 = HIDWORD(KeyValueInformation);
    }
    else
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          110,
          &WPP_c1878895bf8430c1024ddd3cf0a685b6_Traceguids,
          DestinationString.Buffer);
      return -1073741823;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180017650  push    rbp
0x180017652  push    rbx
0x180017653  push    rdi
0x180017654  lea     rbp, [rsp-180h]
0x18001765c  sub     rsp, 280h
0x180017663  mov     rax, cs:__security_cookie
0x18001766a  xor     rax, rsp
0x18001766d  mov     [rbp+190h+var_20], rax
0x180017674  mov     [rsp+290h+var_260], 0
0x18001767c  xorps   xmm0, xmm0
0x18001767f  xorps   xmm1, xmm1
0x180017682  mov     rbx, r9
0x180017685  mov     r11, r8
0x180017688  mov     rdi, rcx
0x18001768b  movups  xmmword ptr [rsp+290h+DestinationString.Length], xmm0
0x180017690  movups  [rsp+290h+KeyValueInformation], xmm1
0x180017695  test    rdx, rdx
0x180017698  jz      short loc_1800176C0
0x18001769a  mov     r9, rdx; pszSrc
0x18001769d  lea     rcx, [rsp+290h+pszDest]; pszDest
0x1800176a2  mov     edx, 104h; cchDest
0x1800176a7  call    StringCopyWorkerW_0
0x1800176ac  mov     r8, r11; pszSrc
0x1800176af  lea     rcx, [rsp+290h+pszDest]; pszDest
0x1800176b4  call    StringCchCatW
0x1800176b9  lea     rdx, [rsp+290h+pszDest]
0x1800176be  jmp     short loc_1800176C3
0x1800176c0  mov     rdx, r11; SourceString
0x1800176c3  lea     rcx, [rsp+290h+DestinationString]; DestinationString
0x1800176c8  call    cs:__imp_RtlInitUnicodeString
0x1800176ce  lea     rax, [rsp+290h+var_260]
0x1800176d3  mov     r8d, 2; KeyValueInformationClass
0x1800176d9  mov     [rsp+290h+ResultLength], rax; ResultLength
0x1800176de  lea     r9, [rsp+290h+KeyValueInformation]; KeyValueInformation
0x1800176e3  lea     rdx, [rsp+290h+DestinationString]; ValueName
0x1800176e8  mov     dword ptr [rsp+290h+Length], 10h; Length
0x1800176f0  mov     rcx, rdi; KeyHandle
0x1800176f3  call    cs:__imp_NtQueryValueKey
0x1800176f9  test    eax, eax
0x1800176fb  js      short loc_180017745
0x1800176fd  cmp     dword ptr [rsp+290h+KeyValueInformation+4], 4
0x180017702  jnz     short loc_180017713
0x180017704  cmp     dword ptr [rsp+290h+KeyValueInformation+8], 4
0x180017709  jnz     short loc_180017713
0x18001770b  mov     ecx, dword ptr [rsp+290h+KeyValueInformation+0Ch]
0x18001770f  mov     [rbx], ecx
0x180017711  jmp     short loc_180017745
0x180017713  mov     rcx, cs:WPP_GLOBAL_Control
0x18001771a  test    byte ptr [rcx+1Ch], 1
0x18001771e  jz      short loc_180017740
0x180017720  cmp     byte ptr [rcx+19h], 2
0x180017724  jb      short loc_180017740
0x180017726  mov     r9, [rsp+290h+DestinationString.Buffer]
0x18001772b  lea     r8, WPP_c1878895bf8430c1024ddd3cf0a685b6_Traceguids
0x180017732  mov     rcx, [rcx+10h]
0x180017736  mov     edx, 6Eh ; 'n'
0x18001773b  call    WPP_SF_S
0x180017740  mov     eax, 0C0000001h
0x180017745  mov     rcx, [rbp+190h+var_20]
0x18001774c  xor     rcx, rsp; StackCookie
0x18001774f  call    __security_check_cookie
0x180017754  add     rsp, 280h
0x18001775b  pop     rdi
0x18001775c  pop     rbx
0x18001775d  pop     rbp
0x18001775e  retn
```
