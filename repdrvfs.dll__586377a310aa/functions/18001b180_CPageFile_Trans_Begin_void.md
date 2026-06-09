# CPageFile::Trans_Begin(void)

- ea: `0x18001b180`
- end: `0x18001b26a`
- name: `?Trans_Begin@CPageFile@@QEAAKXZ`
- size: `234`
- prototype: `unsigned int __fastcall(CPageFile *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001aaf0`

## callees

- `0x1800012b8`
- `0x18001b180`
- `0x18001b270`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18001b196`
- `wbemcomn!GetMemLogObject` at `0x18001b1fe`
- `wbemcomn!GetMemLogObject` at `0x18001b196`
- `wbemcomn!GetMemLogObject` at `0x18001b1fe`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001b1a6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001b209`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001b1a6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001b209`

## pseudocode

```c
__int64 __fastcall CPageFile::Trans_Begin(CPageFile *this)
{
  CMemoryLog *MemLogObject; // rax
  __int64 result; // rax
  unsigned int v4; // eax
  unsigned int v5; // edi
  CMemoryLog *v6; // rax

  if ( *((_DWORD *)this + 49) )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, 4317);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, 4317);
    }
    return 4317;
  }
  else
  {
    v4 = CPageFile::ResyncMaps(this, 0);
    *((_DWORD *)this + 54) = 0;
    v5 = v4;
    if ( v4 )
    {
      v6 = GetMemLogObject();
      CMemoryLog::Write(v6, v5);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, v5);
      }
      return v5;
    }
    else
    {
      *((_DWORD *)this + 48) = *((_DWORD *)this + 24);
      result = 0;
      *((_DWORD *)this + 49) = 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001b180  mov     [rsp+arg_0], rbx
0x18001b185  push    rdi
0x18001b186  sub     rsp, 20h
0x18001b18a  cmp     dword ptr [rcx+0C4h], 0
0x18001b191  mov     rbx, rcx
0x18001b194  jz      short loc_18001B1E7
0x18001b196  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001b19c  mov     ebx, 10DDh
0x18001b1a1  mov     rcx, rax
0x18001b1a4  mov     edx, ebx
0x18001b1a6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001b1ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b1b3  lea     rax, WPP_GLOBAL_Control
0x18001b1ba  cmp     rcx, rax
0x18001b1bd  jz      short loc_18001B1E3
0x18001b1bf  test    byte ptr [rcx+1Ch], 1
0x18001b1c3  jz      short loc_18001B1E3
0x18001b1c5  cmp     byte ptr [rcx+19h], 2
0x18001b1c9  jb      short loc_18001B1E3
0x18001b1cb  mov     rcx, [rcx+10h]
0x18001b1cf  lea     r8, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids
0x18001b1d6  mov     edx, 44h ; 'D'
0x18001b1db  mov     r9d, ebx
0x18001b1de  call    WPP_SF_d
0x18001b1e3  mov     eax, ebx
0x18001b1e5  jmp     short loc_18001B25F
0x18001b1e7  xor     edx, edx; bool
0x18001b1e9  call    ?ResyncMaps@CPageFile@@QEAAK_N@Z; CPageFile::ResyncMaps(bool)
0x18001b1ee  mov     dword ptr [rbx+0D8h], 0
0x18001b1f8  mov     edi, eax
0x18001b1fa  test    eax, eax
0x18001b1fc  jz      short loc_18001B24A
0x18001b1fe  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001b204  mov     rcx, rax
0x18001b207  mov     edx, edi
0x18001b209  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001b20f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b216  lea     rax, WPP_GLOBAL_Control
0x18001b21d  cmp     rcx, rax
0x18001b220  jz      short loc_18001B246
0x18001b222  test    byte ptr [rcx+1Ch], 1
0x18001b226  jz      short loc_18001B246
0x18001b228  cmp     byte ptr [rcx+19h], 2
0x18001b22c  jb      short loc_18001B246
0x18001b22e  mov     rcx, [rcx+10h]
0x18001b232  lea     r8, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids
0x18001b239  mov     edx, 45h ; 'E'
0x18001b23e  mov     r9d, edi
0x18001b241  call    WPP_SF_d
0x18001b246  mov     eax, edi
0x18001b248  jmp     short loc_18001B25F
0x18001b24a  mov     eax, [rbx+60h]
0x18001b24d  mov     [rbx+0C0h], eax
0x18001b253  xor     eax, eax
0x18001b255  mov     dword ptr [rbx+0C4h], 1
0x18001b25f  mov     rbx, [rsp+28h+arg_0]
0x18001b264  add     rsp, 20h
0x18001b268  pop     rdi
0x18001b269  retn
```
