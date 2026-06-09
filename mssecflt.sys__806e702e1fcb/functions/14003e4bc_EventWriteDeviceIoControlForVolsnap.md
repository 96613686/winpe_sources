# EventWriteDeviceIoControlForVolsnap

- ea: `0x14003e4bc`
- end: `0x14003e638`
- name: `EventWriteDeviceIoControlForVolsnap`
- size: `380`
- prototype: `__int64 __fastcall(int, int, int, int, char, wchar_t *Str, wchar_t *, char, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14003e638`

## callees

- `0x140008714`
- `0x14000876c`
- `0x14001008c`
- `0x14003e4bc`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x14003e616`
- `ntoskrnl!EtwWrite` at `0x14003e616`

## pseudocode

```c
__int64 __fastcall EventWriteDeviceIoControlForVolsnap(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        char a5,
        wchar_t *Str,
        wchar_t *a7,
        char a8,
        __int64 a9)
{
  PSLIST_ENTRY EtwDescriptorBuffer; // rax
  PSLIST_ENTRY UserData; // rdi
  const wchar_t *v12; // rbx
  int v13; // esi
  int v14; // ecx
  const WCHAR *v15; // rbp
  const WCHAR *v16; // rax
  const wchar_t *v17; // rbx
  bool v18; // zf
  int v19; // eax
  __int64 v20; // rcx
  GUID *v21; // rax
  unsigned int v22; // ebx
  __int64 v23; // [rsp+60h] [rbp+8h] BYREF
  int v24; // [rsp+68h] [rbp+10h] BYREF
  __int64 v25; // [rsp+70h] [rbp+18h] BYREF
  __int64 v26; // [rsp+78h] [rbp+20h] BYREF

  v26 = a4;
  v25 = a3;
  v24 = a2;
  v23 = a1;
  EtwDescriptorBuffer = SecGetEtwDescriptorBuffer(9u);
  UserData = EtwDescriptorBuffer;
  if ( !EtwDescriptorBuffer )
    return 3221225495LL;
  v12 = Str;
  EtwDescriptorBuffer->Next = (struct _SLIST_ENTRY *)&v23;
  EtwDescriptorBuffer[1].Next = (struct _SLIST_ENTRY *)&v24;
  EtwDescriptorBuffer[2].Next = (struct _SLIST_ENTRY *)&v25;
  EtwDescriptorBuffer[3].Next = (struct _SLIST_ENTRY *)&v26;
  EtwDescriptorBuffer[4].Next = (struct _SLIST_ENTRY *)&a5;
  v13 = 2;
  *((_QWORD *)&EtwDescriptorBuffer->Next + 1) = 8;
  *((_QWORD *)&EtwDescriptorBuffer[1].Next + 1) = 4;
  *((_QWORD *)&EtwDescriptorBuffer[2].Next + 1) = 8;
  *((_QWORD *)&EtwDescriptorBuffer[3].Next + 1) = 8;
  *((_QWORD *)&EtwDescriptorBuffer[4].Next + 1) = 4;
  if ( v12 )
    v14 = 2 * wcslen_0(v12) + 2;
  else
    v14 = 2;
  *((_DWORD *)&UserData[5].Next + 2) = v14;
  v15 = &SourceString;
  *((_DWORD *)&UserData[5].Next + 3) = 0;
  v16 = &SourceString;
  if ( v12 )
    v16 = v12;
  v17 = a7;
  UserData[5].Next = (struct _SLIST_ENTRY *)v16;
  v18 = v17 == 0;
  if ( v17 )
  {
    v19 = wcslen_0(v17);
    v18 = v17 == 0;
    v13 = 2 * v19 + 2;
  }
  v20 = a9;
  if ( !v18 )
    v15 = v17;
  UserData[7].Next = (struct _SLIST_ENTRY *)&a8;
  UserData[6].Next = (struct _SLIST_ENTRY *)v15;
  *((_DWORD *)&UserData[6].Next + 2) = v13;
  v21 = &GUID_NULL;
  if ( v20 )
    v21 = (GUID *)v20;
  *((_DWORD *)&UserData[6].Next + 3) = 0;
  UserData[8].Next = (struct _SLIST_ENTRY *)v21;
  *((_QWORD *)&UserData[7].Next + 1) = 8;
  *((_QWORD *)&UserData[8].Next + 1) = 16;
  v22 = EtwWrite(Microsoft_Windows_SECHandle, &Event47, 0, 9u, (PEVENT_DATA_DESCRIPTOR)UserData);
  SecReleaseEtwDescriptorBuffer(UserData);
  return v22;
}

```

## disassembly

```asm
0x14003e4bc  mov     rax, rsp
0x14003e4bf  mov     [rax+20h], r9
0x14003e4c3  mov     [rax+18h], r8
0x14003e4c7  mov     [rax+10h], edx
0x14003e4ca  mov     [rax+8], rcx
0x14003e4ce  push    rbx
0x14003e4cf  push    rbp
0x14003e4d0  push    rsi
0x14003e4d1  push    rdi
0x14003e4d2  sub     rsp, 38h
0x14003e4d6  mov     ecx, 9
0x14003e4db  call    SecGetEtwDescriptorBuffer
0x14003e4e0  mov     rdi, rax
0x14003e4e3  test    rax, rax
0x14003e4e6  jnz     short loc_14003E4F2
0x14003e4e8  mov     eax, 0C0000017h
0x14003e4ed  jmp     loc_14003E62E
0x14003e4f2  mov     rbx, [rsp+58h+Str]
0x14003e4fa  lea     rax, [rsp+58h+arg_0]
0x14003e4ff  mov     [rdi], rax
0x14003e502  lea     rax, [rsp+58h+arg_8]
0x14003e507  mov     [rdi+10h], rax
0x14003e50b  lea     rax, [rsp+58h+arg_10]
0x14003e510  mov     [rdi+20h], rax
0x14003e514  lea     rax, [rsp+58h+arg_18]
0x14003e519  mov     [rdi+30h], rax
0x14003e51d  lea     rax, [rsp+58h+arg_20]
0x14003e525  mov     [rdi+40h], rax
0x14003e529  mov     esi, 2
0x14003e52e  mov     qword ptr [rdi+8], 8
0x14003e536  mov     qword ptr [rdi+18h], 4
0x14003e53e  mov     qword ptr [rdi+28h], 8
0x14003e546  mov     qword ptr [rdi+38h], 8
0x14003e54e  mov     qword ptr [rdi+48h], 4
0x14003e556  test    rbx, rbx
0x14003e559  jz      short loc_14003E56C
0x14003e55b  mov     rcx, rbx; Str
0x14003e55e  call    wcslen_0
0x14003e563  lea     ecx, ds:2[rax*2]
0x14003e56a  jmp     short loc_14003E56E
0x14003e56c  mov     ecx, esi
0x14003e56e  test    rbx, rbx
0x14003e571  mov     [rdi+58h], ecx
0x14003e574  lea     rbp, SourceString
0x14003e57b  mov     dword ptr [rdi+5Ch], 0
0x14003e582  mov     rax, rbp
0x14003e585  cmovnz  rax, rbx
0x14003e589  mov     rbx, [rsp+58h+arg_30]
0x14003e591  mov     [rdi+50h], rax
0x14003e595  test    rbx, rbx
0x14003e598  jz      short loc_14003E5AC
0x14003e59a  mov     rcx, rbx; Str
0x14003e59d  call    wcslen_0
0x14003e5a2  test    rbx, rbx
0x14003e5a5  lea     esi, ds:2[rax*2]
0x14003e5ac  mov     rcx, [rsp+58h+arg_40]
0x14003e5b4  lea     rax, [rsp+58h+arg_38]
0x14003e5bc  cmovnz  rbp, rbx
0x14003e5c0  mov     [rdi+70h], rax
0x14003e5c4  test    rcx, rcx
0x14003e5c7  mov     [rdi+60h], rbp
0x14003e5cb  mov     [rdi+68h], esi
0x14003e5ce  lea     rax, GUID_NULL
0x14003e5d5  cmovnz  rax, rcx
0x14003e5d9  mov     dword ptr [rdi+6Ch], 0
0x14003e5e0  mov     [rdi+80h], rax
0x14003e5e7  lea     rdx, Event47; EventDescriptor
0x14003e5ee  mov     qword ptr [rdi+78h], 8
0x14003e5f6  mov     r9d, 9; UserDataCount
0x14003e5fc  mov     qword ptr [rdi+88h], 10h
0x14003e607  xor     r8d, r8d; ActivityId
0x14003e60a  mov     rcx, cs:Microsoft_Windows_SECHandle; RegHandle
0x14003e611  mov     [rsp+58h+UserData], rdi; UserData
0x14003e616  call    cs:__imp_EtwWrite
0x14003e61d  nop     dword ptr [rax+rax+00h]
0x14003e622  mov     rcx, rdi; ListEntry
0x14003e625  mov     ebx, eax
0x14003e627  call    SecReleaseEtwDescriptorBuffer
0x14003e62c  mov     eax, ebx
0x14003e62e  add     rsp, 38h
0x14003e632  pop     rdi
0x14003e633  pop     rsi
0x14003e634  pop     rbp
0x14003e635  pop     rbx
0x14003e636  retn
```
