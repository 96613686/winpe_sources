# NcaSrcLnkdTriggerUnregisterWait

- ea: `0x18000b3a8`
- end: `0x18000b480`
- name: `NcaSrcLnkdTriggerUnregisterWait`
- size: `216`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, struct _LIST_ENTRY *)`
- caller_count: `10`
- callee_count: `6`
- tags: ``

## callers

- `0x180006b10`
- `0x18000b1e8`
- `0x18000e170`
- `0x18000eb28`
- `0x180010600`
- `0x1800109b0`
- `0x180010de0`
- `0x180011bc0`
- `0x180014520`
- `0x180014aa0`

## callees

- `0x180003770`
- `0x180004f04`
- `0x180004f34`
- `0x18000b128`
- `0x18000b3a8`
- `0x18000b6d8`

## pseudocode

```c
__int64 __fastcall NcaSrcLnkdTriggerUnregisterWait(LPCRITICAL_SECTION lpCriticalSection, struct _LIST_ENTRY *a2)
{
  PVOID *v4; // rcx
  unsigned int v5; // edi

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    v5 = 0;
    if ( HIDWORD(a2[1].Flink) == 1 )
    {
      NcaSrcLnkdTriggerUnregisterFromSource(lpCriticalSection, a2);
      HIDWORD(a2[1].Flink) = 0;
    }
    if ( LODWORD(a2[2].Flink) == 1 )
      NcaTriggerUnregisterWait(a2[1].Blink);
    else
      a2[1].Blink = 0;
    NcaFree(a2);
    goto LABEL_14;
  }
  v5 = 87;
  if ( v4 == &WPP_GLOBAL_Control )
    return v5;
  if ( (*((_BYTE *)v4 + 28) & 1) != 0 )
  {
    WPP_SF_d(v4[2], 34, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids, 87);
LABEL_14:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 )
    WPP_SF_d(v4[2], 35, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x18000b3a8  push    rbx
0x18000b3aa  push    rbp
0x18000b3ab  push    rsi
0x18000b3ac  push    rdi
0x18000b3ad  sub     rsp, 28h
0x18000b3b1  mov     rbx, rdx
0x18000b3b4  mov     rsi, rcx
0x18000b3b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b3be  lea     rbp, WPP_GLOBAL_Control
0x18000b3c5  cmp     rcx, rbp
0x18000b3c8  jz      short loc_18000B3EC
0x18000b3ca  test    byte ptr [rcx+1Ch], 8
0x18000b3ce  jz      short loc_18000B3EC
0x18000b3d0  mov     rcx, [rcx+10h]
0x18000b3d4  lea     r8, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids
0x18000b3db  mov     edx, 21h ; '!'
0x18000b3e0  call    WPP_SF_
0x18000b3e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b3ec  test    rbx, rbx
0x18000b3ef  jnz     short loc_18000B417
0x18000b3f1  lea     edi, [rbx+57h]
0x18000b3f4  cmp     rcx, rbp
0x18000b3f7  jz      short loc_18000B474
0x18000b3f9  test    byte ptr [rcx+1Ch], 1
0x18000b3fd  jz      short loc_18000B451
0x18000b3ff  mov     rcx, [rcx+10h]
0x18000b403  lea     edx, [rbx+22h]
0x18000b406  mov     r9d, edi
0x18000b409  lea     r8, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids
0x18000b410  call    WPP_SF_d
0x18000b415  jmp     short loc_18000B44A
0x18000b417  xor     edi, edi
0x18000b419  cmp     dword ptr [rbx+14h], 1
0x18000b41d  jnz     short loc_18000B42D
0x18000b41f  mov     rdx, rbx; struct _LIST_ENTRY *
0x18000b422  mov     rcx, rsi; lpCriticalSection
0x18000b425  call    ?NcaSrcLnkdTriggerUnregisterFromSource@@YAXPEAUNCA_SYNCED_LIST_HEAD_@@PEAU_LIST_ENTRY@@@Z; NcaSrcLnkdTriggerUnregisterFromSource(NCA_SYNCED_LIST_HEAD_ *,_LIST_ENTRY *)
0x18000b42a  mov     [rbx+14h], edi
0x18000b42d  cmp     dword ptr [rbx+20h], 1
0x18000b431  jnz     short loc_18000B43E
0x18000b433  mov     rcx, [rbx+18h]; lpMem
0x18000b437  call    NcaTriggerUnregisterWait
0x18000b43c  jmp     short loc_18000B442
0x18000b43e  mov     [rbx+18h], rdi
0x18000b442  mov     rcx, rbx; lpMem
0x18000b445  call    NcaFree
0x18000b44a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b451  cmp     rcx, rbp
0x18000b454  jz      short loc_18000B474
0x18000b456  test    byte ptr [rcx+1Ch], 8
0x18000b45a  jz      short loc_18000B474
0x18000b45c  mov     rcx, [rcx+10h]
0x18000b460  lea     r8, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids
0x18000b467  mov     edx, 23h ; '#'
0x18000b46c  mov     r9d, edi
0x18000b46f  call    WPP_SF_d
0x18000b474  mov     eax, edi
0x18000b476  add     rsp, 28h
0x18000b47a  pop     rdi
0x18000b47b  pop     rsi
0x18000b47c  pop     rbp
0x18000b47d  pop     rbx
0x18000b47e  retn
```
