# CPageSource::RollbackTrans(void)

- ea: `0x18002f9ac`
- end: `0x18002fb03`
- name: `?RollbackTrans@CPageSource@@QEAAKXZ`
- size: `343`
- prototype: `unsigned int __fastcall(CPageSource *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001b578`
- `0x18001b5c0`
- `0x180031128`
- `0x18003dbf8`

## callees

- `0x1800012b8`
- `0x18002f9ac`
- `0x1800302e8`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18002f9cb`
- `wbemcomn!GetMemLogObject` at `0x18002fa29`
- `wbemcomn!GetMemLogObject` at `0x18002fa6e`
- `wbemcomn!GetMemLogObject` at `0x18002f9cb`
- `wbemcomn!GetMemLogObject` at `0x18002fa29`
- `wbemcomn!GetMemLogObject` at `0x18002fa6e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002f9d6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002fa34`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002fa7e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002f9d6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002fa34`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002fa7e`

## pseudocode

```c
__int64 __fastcall CPageSource::RollbackTrans(CPageSource *this)
{
  unsigned int v2; // edi
  CMemoryLog *MemLogObject; // rax
  CVarObjHeap *v4; // rcx
  __int64 v5; // rdx
  CMemoryLog *v7; // rax
  CMemoryLog *v8; // rax

  v2 = CPageFile::Trans_Rollback((CPageSource *)((char *)this + 488));
  if ( v2 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v2);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v2;
    }
    v5 = 117;
LABEL_6:
    WPP_SF_d(*((_QWORD *)v4 + 2), v5, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, v2);
    return v2;
  }
  v2 = CPageFile::Trans_Rollback((CPageSource *)((char *)this + 32));
  if ( v2 )
  {
    v7 = GetMemLogObject();
    CMemoryLog::Write(v7, v2);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v2;
    }
    v5 = 118;
    goto LABEL_6;
  }
  if ( *((_DWORD *)this + 59) == *((_DWORD *)this + 173) )
  {
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 120, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, 0);
    }
    return 0;
  }
  else
  {
    v8 = GetMemLogObject();
    CMemoryLog::Write(v8, 1306);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 119, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, 1306);
    }
    return 1306;
  }
}

```

## disassembly

```asm
0x18002f9ac  mov     [rsp+arg_0], rbx
0x18002f9b1  push    rdi
0x18002f9b2  sub     rsp, 20h
0x18002f9b6  mov     rbx, rcx
0x18002f9b9  add     rcx, 1E8h; this
0x18002f9c0  call    ?Trans_Rollback@CPageFile@@QEAAKXZ; CPageFile::Trans_Rollback(void)
0x18002f9c5  mov     edi, eax
0x18002f9c7  test    eax, eax
0x18002f9c9  jz      short loc_18002FA1A
0x18002f9cb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002f9d1  mov     rcx, rax
0x18002f9d4  mov     edx, edi
0x18002f9d6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002f9dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f9e3  lea     rdx, WPP_GLOBAL_Control
0x18002f9ea  cmp     rcx, rdx
0x18002f9ed  jz      short loc_18002FA13
0x18002f9ef  test    byte ptr [rcx+1Ch], 1
0x18002f9f3  jz      short loc_18002FA13
0x18002f9f5  cmp     byte ptr [rcx+19h], 2
0x18002f9f9  jb      short loc_18002FA13
0x18002f9fb  mov     edx, 75h ; 'u'
0x18002fa00  mov     rcx, [rcx+10h]
0x18002fa04  lea     r8, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids
0x18002fa0b  mov     r9d, edi
0x18002fa0e  call    WPP_SF_d
0x18002fa13  mov     eax, edi
0x18002fa15  jmp     loc_18002FAF8
0x18002fa1a  lea     rcx, [rbx+20h]; this
0x18002fa1e  call    ?Trans_Rollback@CPageFile@@QEAAKXZ; CPageFile::Trans_Rollback(void)
0x18002fa23  mov     edi, eax
0x18002fa25  test    eax, eax
0x18002fa27  jz      short loc_18002FA60
0x18002fa29  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002fa2f  mov     rcx, rax
0x18002fa32  mov     edx, edi
0x18002fa34  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002fa3a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fa41  lea     rdx, WPP_GLOBAL_Control
0x18002fa48  cmp     rcx, rdx
0x18002fa4b  jz      short loc_18002FA13
0x18002fa4d  test    byte ptr [rcx+1Ch], 1
0x18002fa51  jz      short loc_18002FA13
0x18002fa53  cmp     byte ptr [rcx+19h], 2
0x18002fa57  jb      short loc_18002FA13
0x18002fa59  mov     edx, 76h ; 'v'
0x18002fa5e  jmp     short loc_18002FA00
0x18002fa60  mov     eax, [rbx+2B4h]
0x18002fa66  cmp     [rbx+0ECh], eax
0x18002fa6c  jz      short loc_18002FABF
0x18002fa6e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002fa74  mov     ebx, 51Ah
0x18002fa79  mov     rcx, rax
0x18002fa7c  mov     edx, ebx
0x18002fa7e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002fa84  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fa8b  lea     rdx, WPP_GLOBAL_Control
0x18002fa92  cmp     rcx, rdx
0x18002fa95  jz      short loc_18002FABB
0x18002fa97  test    byte ptr [rcx+1Ch], 1
0x18002fa9b  jz      short loc_18002FABB
0x18002fa9d  cmp     byte ptr [rcx+19h], 2
0x18002faa1  jb      short loc_18002FABB
0x18002faa3  mov     rcx, [rcx+10h]
0x18002faa7  lea     r8, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids
0x18002faae  mov     edx, 77h ; 'w'
0x18002fab3  mov     r9d, ebx
0x18002fab6  call    WPP_SF_d
0x18002fabb  mov     eax, ebx
0x18002fabd  jmp     short loc_18002FAF8
0x18002fabf  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fac6  lea     rdx, WPP_GLOBAL_Control
0x18002facd  cmp     rcx, rdx
0x18002fad0  jz      short loc_18002FAF6
0x18002fad2  test    byte ptr [rcx+1Ch], 1
0x18002fad6  jz      short loc_18002FAF6
0x18002fad8  cmp     byte ptr [rcx+19h], 2
0x18002fadc  jb      short loc_18002FAF6
0x18002fade  mov     rcx, [rcx+10h]
0x18002fae2  lea     r8, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids
0x18002fae9  mov     edx, 78h ; 'x'
0x18002faee  xor     r9d, r9d
0x18002faf1  call    WPP_SF_d
0x18002faf6  xor     eax, eax
0x18002faf8  mov     rbx, [rsp+28h+arg_0]
0x18002fafd  add     rsp, 20h
0x18002fb01  pop     rdi
0x18002fb02  retn
```
