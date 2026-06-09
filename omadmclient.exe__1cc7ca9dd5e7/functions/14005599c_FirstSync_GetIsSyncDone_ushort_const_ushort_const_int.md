# FirstSync::GetIsSyncDone(ushort const *,ushort const *,int *)

- ea: `0x14005599c`
- end: `0x140055a61`
- name: `?GetIsSyncDone@FirstSync@@YAJPEBG0PEAH@Z`
- size: `197`
- prototype: `int(FirstSync *__hidden this, const unsigned __int16 *, const unsigned __int16 *, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140048db0`
- `0x14004f290`

## callees

- `0x14000b0f4`
- `0x1400556e8`
- `0x14005599c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140055a4c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140055a4c`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140055a17`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140055a17`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FirstSync::GetIsSyncDone(
        const WCHAR *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        HKEY *a4)
{
  __int64 v5; // rdx
  int FirstSyncKey; // ecx
  unsigned int v8; // edi
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned int v11; // [rsp+30h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+20h] BYREF

  if ( !this )
  {
    v5 = 429;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
      (const char *)0x80070057LL,
      v9);
    return 2147942487LL;
  }
  if ( !a3 )
  {
    v5 = 430;
    goto LABEL_3;
  }
  *(_DWORD *)a3 = 0;
  hKey = 0;
  FirstSyncKey = FirstSync::GetFirstSyncKey(this, a2, (unsigned __int16 *)&hKey, a4);
  v11 = 0;
  if ( FirstSyncKey >= 0 )
  {
    FirstSyncKey = OmaDmRegistryGetDWORD(hKey, 0, L"IsSyncDone", &v11);
    if ( FirstSyncKey >= 0 )
      *(_DWORD *)a3 = v11 != 0;
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
0x14005599c  push    rdi; int
0x14005599e  sub     rsp, 20h
0x1400559a2  mov     rdi, r8
0x1400559a5  test    rcx, rcx
0x1400559a8  jnz     short loc_1400559D0
0x1400559aa  mov     edx, 1ADh; void *
0x1400559af  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1400559b6  mov     r9d, 80070057h; char *
0x1400559bc  mov     rcx, [rsp+28h]; this
0x1400559c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400559c6  mov     eax, 80070057h
0x1400559cb  jmp     loc_140055A5A
0x1400559d0  test    rdi, rdi
0x1400559d3  jnz     short loc_1400559DC
0x1400559d5  mov     edx, 1AEh; PCWSTR
0x1400559da  jmp     short loc_1400559AF
0x1400559dc  mov     dword ptr [r8], 0
0x1400559e3  mov     [rsp+28h+hKey], 0
0x1400559ec  lea     r8, [rsp+28h+hKey]; unsigned __int16 *
0x1400559f1  call    ?GetFirstSyncKey@FirstSync@@YAJPEBG0PEAPEAUHKEY__@@H@Z; FirstSync::GetFirstSyncKey(ushort const *,ushort const *,HKEY__ * *,int)
0x1400559f6  mov     ecx, eax
0x1400559f8  mov     [rsp+28h+arg_0], 0
0x140055a00  test    eax, eax
0x140055a02  js      short loc_140055A34
0x140055a04  lea     r9, [rsp+28h+arg_0]
0x140055a09  lea     r8, aIssyncdone; "IsSyncDone"
0x140055a10  xor     edx, edx
0x140055a12  mov     rcx, [rsp+28h+hKey]
0x140055a17  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x140055a1e  nop     dword ptr [rax+rax+00h]
0x140055a23  mov     ecx, eax
0x140055a25  test    eax, eax
0x140055a27  js      short loc_140055A34
0x140055a29  xor     eax, eax
0x140055a2b  cmp     [rsp+28h+arg_0], eax
0x140055a2f  setnz   al
0x140055a32  mov     [rdi], eax
0x140055a34  xor     edi, edi
0x140055a36  cmp     ecx, 80070002h
0x140055a3c  cmovnz  edi, ecx
0x140055a3f  cmp     [rsp+28h+hKey], 0
0x140055a45  jz      short loc_140055A58
0x140055a47  mov     rcx, [rsp+28h+hKey]; hKey
0x140055a4c  call    cs:__imp_RegCloseKey
0x140055a53  nop     dword ptr [rax+rax+00h]
0x140055a58  mov     eax, edi
0x140055a5a  add     rsp, 20h
0x140055a5e  pop     rdi
0x140055a5f  retn
```
