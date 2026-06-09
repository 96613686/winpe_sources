# CPageSource::BeginTrans(void)

- ea: `0x18001aaf0`
- end: `0x18001abb9`
- name: `?BeginTrans@CPageSource@@QEAAKXZ`
- size: `201`
- prototype: `__int64 __fastcall(CPageSource *this)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001c898`
- `0x18001d7bc`
- `0x180027504`
- `0x18003dbf8`

## callees

- `0x1800012b8`
- `0x18001aaf0`
- `0x18001b180`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18001ab1a`
- `wbemcomn!GetMemLogObject` at `0x18001ab75`
- `wbemcomn!GetMemLogObject` at `0x18001ab1a`
- `wbemcomn!GetMemLogObject` at `0x18001ab75`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001ab25`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001ab80`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001ab25`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001ab80`

## pseudocode

```c
__int64 __fastcall CPageSource::BeginTrans(CPageSource *this)
{
  __int64 result; // rax
  unsigned int v3; // ebx
  CMemoryLog *MemLogObject; // rax
  CVarObjHeap *v5; // rcx
  __int64 v6; // rdx
  CMemoryLog *v7; // rax

  result = *((unsigned int *)this + 1);
  if ( !(_DWORD)result )
  {
    v3 = CPageFile::Trans_Begin((CPageSource *)((char *)this + 488));
    if ( v3 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v3);
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return v3;
      }
      v6 = 101;
LABEL_7:
      WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, v3);
      return v3;
    }
    v3 = CPageFile::Trans_Begin((CPageSource *)((char *)this + 32));
    if ( v3 )
    {
      v7 = GetMemLogObject();
      CMemoryLog::Write(v7, v3);
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return v3;
      }
      v6 = 102;
      goto LABEL_7;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001aaf0  mov     [rsp+arg_0], rbx
0x18001aaf5  push    rdi
0x18001aaf6  sub     rsp, 20h
0x18001aafa  mov     eax, [rcx+4]
0x18001aafd  mov     rdi, rcx
0x18001ab00  test    eax, eax
0x18001ab02  jnz     loc_18001ABAE
0x18001ab08  add     rcx, 1E8h; this
0x18001ab0f  call    ?Trans_Begin@CPageFile@@QEAAKXZ; CPageFile::Trans_Begin(void)
0x18001ab14  mov     ebx, eax
0x18001ab16  test    eax, eax
0x18001ab18  jz      short loc_18001AB66
0x18001ab1a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001ab20  mov     rcx, rax
0x18001ab23  mov     edx, ebx
0x18001ab25  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001ab2b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ab32  lea     rax, WPP_GLOBAL_Control
0x18001ab39  cmp     rcx, rax
0x18001ab3c  jz      short loc_18001AB62
0x18001ab3e  test    byte ptr [rcx+1Ch], 1
0x18001ab42  jz      short loc_18001AB62
0x18001ab44  cmp     byte ptr [rcx+19h], 2
0x18001ab48  jb      short loc_18001AB62
0x18001ab4a  mov     edx, 65h ; 'e'
0x18001ab4f  mov     rcx, [rcx+10h]
0x18001ab53  lea     r8, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids
0x18001ab5a  mov     r9d, ebx
0x18001ab5d  call    WPP_SF_d
0x18001ab62  mov     eax, ebx
0x18001ab64  jmp     short loc_18001ABAE
0x18001ab66  lea     rcx, [rdi+20h]; this
0x18001ab6a  call    ?Trans_Begin@CPageFile@@QEAAKXZ; CPageFile::Trans_Begin(void)
0x18001ab6f  mov     ebx, eax
0x18001ab71  test    eax, eax
0x18001ab73  jz      short loc_18001ABAC
0x18001ab75  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001ab7b  mov     rcx, rax
0x18001ab7e  mov     edx, ebx
0x18001ab80  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001ab86  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ab8d  lea     rax, WPP_GLOBAL_Control
0x18001ab94  cmp     rcx, rax
0x18001ab97  jz      short loc_18001AB62
0x18001ab99  test    byte ptr [rcx+1Ch], 1
0x18001ab9d  jz      short loc_18001AB62
0x18001ab9f  cmp     byte ptr [rcx+19h], 2
0x18001aba3  jb      short loc_18001AB62
0x18001aba5  mov     edx, 66h ; 'f'
0x18001abaa  jmp     short loc_18001AB4F
0x18001abac  xor     eax, eax
0x18001abae  mov     rbx, [rsp+28h+arg_0]
0x18001abb3  add     rsp, 20h
0x18001abb7  pop     rdi
0x18001abb8  retn
```
