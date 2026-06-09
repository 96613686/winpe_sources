# CscScopeCharacteristicsInsert

- ea: `0x140053c8c`
- end: `0x140053e1f`
- name: `CscScopeCharacteristicsInsert`
- size: `403`
- prototype: `__int64 __fastcall(PERESOURCE Resource, PCUNICODE_STRING SourceString, __int64, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14004d248`

## callees

- `0x14001a624`
- `0x1400226a0`
- `0x140053c34`
- `0x140053c8c`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140053d55`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140053d55`
- `ntoskrnl!ExAllocatePool2` at `0x140053cf6`
- `ntoskrnl!ExAllocatePool2` at `0x140053cf6`
- `ntoskrnl!ExReleaseResourceLite` at `0x140053dd2`
- `ntoskrnl!ExReleaseResourceLite` at `0x140053dd2`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140053cb1`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140053cb1`

## pseudocode

```c
__int64 __fastcall CscScopeCharacteristicsInsert(
        PERESOURCE Resource,
        PCUNICODE_STRING SourceString,
        __int64 a3,
        int a4)
{
  unsigned int v8; // ebx
  __int64 v9; // r9
  __int64 Pool2; // rbx
  struct _LIST_ENTRY *Blink; // rcx
  __int64 v12; // rax
  int v13; // r8d
  __int64 v15; // [rsp+80h] [rbp+8h] BYREF

  v15 = 0;
  ExAcquireResourceExclusiveLite(Resource, 1u);
  v8 = CscScopeCharacteristicsFindp(Resource, SourceString, &v15);
  if ( v8 == -1073741275 )
  {
    Pool2 = ExAllocatePool2(258, SourceString->Length + 48LL, 1347646275, v9);
    if ( Pool2 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_0272de200038379efbcb93015e740f42_Traceguids, SourceString);
      *(_QWORD *)(Pool2 + 40) = Pool2 + 48;
      *(_WORD *)(Pool2 + 34) = SourceString->Length;
      RtlCopyUnicodeString((PUNICODE_STRING)(Pool2 + 32), SourceString);
      *(_QWORD *)(Pool2 + 16) = a3;
      *(_DWORD *)(Pool2 + 24) = a4;
      Blink = Resource[1].SystemResourcesList.Blink;
      if ( (PERESOURCE)Blink->Flink != &Resource[1] )
        __fastfail(3u);
      *(_QWORD *)Pool2 = Resource + 1;
      *(_QWORD *)(Pool2 + 8) = Blink;
      Blink->Flink = (struct _LIST_ENTRY *)Pool2;
      Resource[1].SystemResourcesList.Blink = (struct _LIST_ENTRY *)Pool2;
      v8 = 0;
      GlobalHaveScopeCharacteristicsSet = 1;
    }
    else
    {
      v8 = -1073741670;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_0272de200038379efbcb93015e740f42_Traceguids, SourceString);
    v12 = v15;
    *(_QWORD *)(v15 + 16) = a3;
    *(_DWORD *)(v12 + 24) = a4;
  }
  ExReleaseResourceLite(Resource);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_ZDiD(WPP_GLOBAL_Control->AttachedDevice, 13, v13, (_DWORD)SourceString, v8, a3, a4);
  return v8;
}

```

## disassembly

```asm
0x140053c8c  mov     rax, rsp
0x140053c8f  push    rbx
0x140053c90  push    rbp
0x140053c91  push    rsi
0x140053c92  push    rdi
0x140053c93  push    r12
0x140053c95  push    r14
0x140053c97  sub     rsp, 48h
0x140053c9b  mov     rdi, rdx
0x140053c9e  mov     qword ptr [rax+8], 0
0x140053ca6  mov     dl, 1; Wait
0x140053ca8  mov     esi, r9d
0x140053cab  mov     rbp, r8
0x140053cae  mov     r14, rcx
0x140053cb1  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140053cb8  nop     dword ptr [rax+rax+00h]
0x140053cbd  lea     r8, [rsp+78h+arg_0]
0x140053cc5  mov     rdx, rdi
0x140053cc8  mov     rcx, r14
0x140053ccb  call    CscScopeCharacteristicsFindp
0x140053cd0  lea     r12, WPP_GLOBAL_Control
0x140053cd7  mov     ebx, eax
0x140053cd9  cmp     eax, 0C0000225h
0x140053cde  jnz     loc_140053D95
0x140053ce4  movzx   edx, word ptr [rdi]
0x140053ce7  mov     ecx, 102h
0x140053cec  add     rdx, 30h ; '0'
0x140053cf0  mov     r8d, 50537343h
0x140053cf6  call    cs:__imp_ExAllocatePool2
0x140053cfd  nop     dword ptr [rax+rax+00h]
0x140053d02  mov     rbx, rax
0x140053d05  test    rax, rax
0x140053d08  jnz     short loc_140053D14
0x140053d0a  mov     ebx, 0C000009Ah
0x140053d0f  jmp     loc_140053DCF
0x140053d14  mov     rcx, cs:WPP_GLOBAL_Control
0x140053d1b  cmp     rcx, r12
0x140053d1e  jz      short loc_140053D3F
0x140053d20  mov     eax, [rcx+2Ch]
0x140053d23  test    al, 40h
0x140053d25  jz      short loc_140053D3F
0x140053d27  mov     rcx, [rcx+18h]
0x140053d2b  lea     r8, WPP_0272de200038379efbcb93015e740f42_Traceguids
0x140053d32  mov     edx, 0Bh
0x140053d37  mov     r9, rdi
0x140053d3a  call    WPP_SF_Z
0x140053d3f  lea     rax, [rbx+30h]
0x140053d43  mov     rdx, rdi; SourceString
0x140053d46  mov     [rbx+28h], rax
0x140053d4a  lea     rcx, [rbx+20h]; DestinationString
0x140053d4e  movzx   eax, word ptr [rdi]
0x140053d51  mov     [rbx+22h], ax
0x140053d55  call    cs:__imp_RtlCopyUnicodeString
0x140053d5c  nop     dword ptr [rax+rax+00h]
0x140053d61  lea     rax, [r14+68h]
0x140053d65  mov     [rbx+10h], rbp
0x140053d69  mov     [rbx+18h], esi
0x140053d6c  mov     rcx, [rax+8]
0x140053d70  cmp     [rcx], rax
0x140053d73  jz      short loc_140053D7C
0x140053d75  mov     ecx, 3
0x140053d7a  int     29h; Win8: RtlFailFast(ecx)
0x140053d7c  mov     [rbx], rax
0x140053d7f  mov     [rbx+8], rcx
0x140053d83  mov     [rcx], rbx
0x140053d86  mov     [rax+8], rbx
0x140053d8a  xor     ebx, ebx
0x140053d8c  mov     cs:GlobalHaveScopeCharacteristicsSet, 1
0x140053d93  jmp     short loc_140053DCF
0x140053d95  mov     rcx, cs:WPP_GLOBAL_Control
0x140053d9c  cmp     rcx, r12
0x140053d9f  jz      short loc_140053DC0
0x140053da1  mov     eax, [rcx+2Ch]
0x140053da4  test    al, 40h
0x140053da6  jz      short loc_140053DC0
0x140053da8  mov     rcx, [rcx+18h]
0x140053dac  lea     r8, WPP_0272de200038379efbcb93015e740f42_Traceguids
0x140053db3  mov     edx, 0Ch
0x140053db8  mov     r9, rdi
0x140053dbb  call    WPP_SF_Z
0x140053dc0  mov     rax, [rsp+78h+arg_0]
0x140053dc8  mov     [rax+10h], rbp
0x140053dcc  mov     [rax+18h], esi
0x140053dcf  mov     rcx, r14; Resource
0x140053dd2  call    cs:__imp_ExReleaseResourceLite
0x140053dd9  nop     dword ptr [rax+rax+00h]
0x140053dde  mov     rcx, cs:WPP_GLOBAL_Control
0x140053de5  cmp     rcx, r12
0x140053de8  jz      short loc_140053E0F
0x140053dea  mov     eax, [rcx+2Ch]
0x140053ded  test    al, 40h
0x140053def  jz      short loc_140053E0F
0x140053df1  mov     rcx, [rcx+18h]
0x140053df5  mov     edx, 0Dh
0x140053dfa  mov     [rsp+78h+var_48], esi
0x140053dfe  mov     r9, rdi
0x140053e01  mov     [rsp+78h+var_50], rbp
0x140053e06  mov     [rsp+78h+var_58], ebx
0x140053e0a  call    WPP_SF_ZDiD
0x140053e0f  mov     eax, ebx
0x140053e11  add     rsp, 48h
0x140053e15  pop     r14
0x140053e17  pop     r12
0x140053e19  pop     rdi
0x140053e1a  pop     rsi
0x140053e1b  pop     rbp
0x140053e1c  pop     rbx
0x140053e1d  retn
```
