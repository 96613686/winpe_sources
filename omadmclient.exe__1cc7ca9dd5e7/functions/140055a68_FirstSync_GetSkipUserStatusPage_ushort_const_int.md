# FirstSync::GetSkipUserStatusPage(ushort const *,int *)

- ea: `0x140055a68`
- end: `0x140055b2e`
- name: `?GetSkipUserStatusPage@FirstSync@@YAJPEBGPEAH@Z`
- size: `198`
- prototype: `int(FirstSync *__hidden this, const unsigned __int16 *, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140048db0`
- `0x14004f290`

## callees

- `0x14000b0f4`
- `0x1400556e8`
- `0x140055a68`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140055b19`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140055b19`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140055ae4`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140055ae4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FirstSync::GetSkipUserStatusPage(const WCHAR *this, unsigned __int16 *a2, int *a3, HKEY *a4)
{
  __int64 v5; // rdx
  int FirstSyncKey; // ecx
  unsigned int v8; // edi
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned int v11; // [rsp+30h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp+18h] BYREF

  if ( !this )
  {
    v5 = 677;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
      (const char *)0x80070057LL,
      v9);
    return 2147942487LL;
  }
  if ( !a2 )
  {
    v5 = 678;
    goto LABEL_3;
  }
  *(_DWORD *)a2 = 1;
  hKey = 0;
  FirstSyncKey = FirstSync::GetFirstSyncKey(this, 0, (unsigned __int16 *)&hKey, a4);
  v11 = 0;
  if ( FirstSyncKey >= 0 )
  {
    FirstSyncKey = OmaDmRegistryGetDWORD(hKey, 0, L"SkipUserStatusPage", &v11);
    if ( FirstSyncKey >= 0 )
      *(_DWORD *)a2 = v11 != 0;
  }
  v8 = 0;
  if ( FirstSyncKey != -2147024894 )
    v8 = FirstSyncKey;
  if ( hKey )
    RegCloseKey(hKey);
  return v8;
}

```

## disassembly

```asm
0x140055a68  push    rdi; int
0x140055a6a  sub     rsp, 20h
0x140055a6e  mov     rdi, rdx
0x140055a71  test    rcx, rcx
0x140055a74  jnz     short loc_140055A9C
0x140055a76  mov     edx, 2A5h; void *
0x140055a7b  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x140055a82  mov     r9d, 80070057h; char *
0x140055a88  mov     rcx, [rsp+28h]; this
0x140055a8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140055a92  mov     eax, 80070057h
0x140055a97  jmp     loc_140055B27
0x140055a9c  test    rdi, rdi
0x140055a9f  jnz     short loc_140055AA8
0x140055aa1  mov     edx, 2A6h
0x140055aa6  jmp     short loc_140055A7B
0x140055aa8  mov     dword ptr [rdx], 1
0x140055aae  mov     [rsp+28h+hKey], 0
0x140055ab7  lea     r8, [rsp+28h+hKey]; unsigned __int16 *
0x140055abc  xor     edx, edx; PCWSTR
0x140055abe  call    ?GetFirstSyncKey@FirstSync@@YAJPEBG0PEAPEAUHKEY__@@H@Z; FirstSync::GetFirstSyncKey(ushort const *,ushort const *,HKEY__ * *,int)
0x140055ac3  mov     ecx, eax
0x140055ac5  mov     [rsp+28h+arg_0], 0
0x140055acd  test    eax, eax
0x140055acf  js      short loc_140055B01
0x140055ad1  lea     r9, [rsp+28h+arg_0]
0x140055ad6  lea     r8, aSkipuserstatus; "SkipUserStatusPage"
0x140055add  xor     edx, edx
0x140055adf  mov     rcx, [rsp+28h+hKey]
0x140055ae4  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x140055aeb  nop     dword ptr [rax+rax+00h]
0x140055af0  mov     ecx, eax
0x140055af2  test    eax, eax
0x140055af4  js      short loc_140055B01
0x140055af6  xor     eax, eax
0x140055af8  cmp     [rsp+28h+arg_0], eax
0x140055afc  setnz   al
0x140055aff  mov     [rdi], eax
0x140055b01  xor     edi, edi
0x140055b03  cmp     ecx, 80070002h
0x140055b09  cmovnz  edi, ecx
0x140055b0c  cmp     [rsp+28h+hKey], 0
0x140055b12  jz      short loc_140055B25
0x140055b14  mov     rcx, [rsp+28h+hKey]; hKey
0x140055b19  call    cs:__imp_RegCloseKey
0x140055b20  nop     dword ptr [rax+rax+00h]
0x140055b25  mov     eax, edi
0x140055b27  add     rsp, 20h
0x140055b2b  pop     rdi
0x140055b2c  retn
```
