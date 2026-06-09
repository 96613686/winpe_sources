# EnsureDirectory(ushort const *,_SECURITY_ATTRIBUTES *)

- ea: `0x180036fd8`
- end: `0x1800370f9`
- name: `?EnsureDirectory@@YAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `289`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003a730`

## callees

- `0x1800012b8`
- `0x180036fd8`

## import_xrefs

- `wbemcomn!WinPEKey` at `0x180037006`
- `wbemcomn!WinPEKey` at `0x180037006`
- `wbemcomn!GetMemLogObject` at `0x180037048`
- `wbemcomn!GetMemLogObject` at `0x180037048`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180037053`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180037053`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180036fe0`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180036fe0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036fee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036fee`

## pseudocode

```c
__int64 __fastcall EnsureDirectory(const unsigned __int16 *a1, struct _SECURITY_ATTRIBUTES *a2)
{
  DWORD LastError; // eax
  DWORD v3; // ebx
  CVarObjHeap *v4; // rcx
  __int64 v5; // rdx
  CMemoryLog *MemLogObject; // rax

  if ( CreateDirectoryW(a1, 0) )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v5 = 14;
    goto LABEL_24;
  }
  LastError = GetLastError();
  v3 = LastError;
  switch ( LastError )
  {
    case 0xB7u:
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 0;
      }
      v5 = 13;
      goto LABEL_24;
    case 5u:
      if ( WinPEKey() == 1 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return 0;
        }
        v5 = v3 + 6;
LABEL_24:
        WPP_SF_d(*((_QWORD *)v4 + 2), v5, WPP_bd119d54cf9d3765d9d03f2987f6593e_Traceguids, 0);
        return 0;
      }
      break;
    case 0u:
      goto LABEL_11;
  }
  MemLogObject = GetMemLogObject();
  CMemoryLog::Write(MemLogObject, v3);
LABEL_11:
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_bd119d54cf9d3765d9d03f2987f6593e_Traceguids, v3);
  }
  return v3;
}

```

## disassembly

```asm
0x180036fd8  push    rbx
0x180036fda  sub     rsp, 20h
0x180036fde  xor     edx, edx; lpSecurityAttributes
0x180036fe0  call    cs:__imp_CreateDirectoryW
0x180036fe6  test    eax, eax
0x180036fe8  jnz     loc_1800370BA
0x180036fee  call    cs:__imp_GetLastError
0x180036ff4  mov     ebx, eax
0x180036ff6  cmp     eax, 0B7h
0x180036ffb  jz      loc_180037094
0x180037001  cmp     eax, 5
0x180037004  jnz     short loc_180037044
0x180037006  call    cs:__imp_?WinPEKey@@YAHXZ; WinPEKey(void)
0x18003700c  cmp     eax, 1
0x18003700f  jnz     short loc_180037048
0x180037011  mov     rcx, cs:WPP_GLOBAL_Control
0x180037018  lea     rax, WPP_GLOBAL_Control
0x18003701f  cmp     rcx, rax
0x180037022  jz      loc_1800370F1
0x180037028  test    byte ptr [rcx+1Ch], 1
0x18003702c  jz      loc_1800370F1
0x180037032  cmp     byte ptr [rcx+19h], 2
0x180037036  jb      loc_1800370F1
0x18003703c  lea     edx, [rbx+6]
0x18003703f  jmp     loc_1800370DE
0x180037044  test    ebx, ebx
0x180037046  jz      short loc_180037059
0x180037048  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003704e  mov     rcx, rax
0x180037051  mov     edx, ebx
0x180037053  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180037059  mov     rcx, cs:WPP_GLOBAL_Control
0x180037060  lea     rax, WPP_GLOBAL_Control
0x180037067  cmp     rcx, rax
0x18003706a  jz      short loc_180037090
0x18003706c  test    byte ptr [rcx+1Ch], 1
0x180037070  jz      short loc_180037090
0x180037072  cmp     byte ptr [rcx+19h], 2
0x180037076  jb      short loc_180037090
0x180037078  mov     rcx, [rcx+10h]
0x18003707c  lea     r8, WPP_bd119d54cf9d3765d9d03f2987f6593e_Traceguids
0x180037083  mov     edx, 0Ch
0x180037088  mov     r9d, ebx
0x18003708b  call    WPP_SF_d
0x180037090  mov     eax, ebx
0x180037092  jmp     short loc_1800370F3
0x180037094  mov     rcx, cs:WPP_GLOBAL_Control
0x18003709b  lea     rax, WPP_GLOBAL_Control
0x1800370a2  cmp     rcx, rax
0x1800370a5  jz      short loc_1800370F1
0x1800370a7  test    byte ptr [rcx+1Ch], 1
0x1800370ab  jz      short loc_1800370F1
0x1800370ad  cmp     byte ptr [rcx+19h], 2
0x1800370b1  jb      short loc_1800370F1
0x1800370b3  mov     edx, 0Dh
0x1800370b8  jmp     short loc_1800370DE
0x1800370ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800370c1  lea     rax, WPP_GLOBAL_Control
0x1800370c8  cmp     rcx, rax
0x1800370cb  jz      short loc_1800370F1
0x1800370cd  test    byte ptr [rcx+1Ch], 1
0x1800370d1  jz      short loc_1800370F1
0x1800370d3  cmp     byte ptr [rcx+19h], 2
0x1800370d7  jb      short loc_1800370F1
0x1800370d9  mov     edx, 0Eh
0x1800370de  mov     rcx, [rcx+10h]
0x1800370e2  lea     r8, WPP_bd119d54cf9d3765d9d03f2987f6593e_Traceguids
0x1800370e9  xor     r9d, r9d
0x1800370ec  call    WPP_SF_d
0x1800370f1  xor     eax, eax
0x1800370f3  add     rsp, 20h
0x1800370f7  pop     rbx
0x1800370f8  retn
```
