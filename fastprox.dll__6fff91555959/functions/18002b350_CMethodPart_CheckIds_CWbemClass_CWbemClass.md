# CMethodPart::CheckIds(CWbemClass *,CWbemClass *)

- ea: `0x18002b350`
- end: `0x18002b4f3`
- name: `?CheckIds@CMethodPart@@IEAAJPEAVCWbemClass@@0@Z`
- size: `419`
- prototype: `int(CMethodPart *__hidden this, struct CWbemClass *, struct CWbemClass *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002ca70`

## callees

- `0x18002b350`
- `0x18002d360`
- `0x180037120`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18002b414`
- `wbemcomn!GetMemLogObject` at `0x18002b44b`
- `wbemcomn!GetMemLogObject` at `0x18002b491`
- `wbemcomn!GetMemLogObject` at `0x18002b414`
- `wbemcomn!GetMemLogObject` at `0x18002b44b`
- `wbemcomn!GetMemLogObject` at `0x18002b491`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18002b3b3`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18002b3b3`
- `wbemcomn!?Sort@CFlexArray@@QEAAXXZ` at `0x18002b3a6`
- `wbemcomn!?Sort@CFlexArray@@QEAAXXZ` at `0x18002b3a6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002b41f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002b456`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002b4a1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002b41f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002b456`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002b4a1`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x18002b3c4`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x18002b3c4`
- `wbemcomn!??0CFlexArray@@QEAA@HH@Z` at `0x18002b376`
- `wbemcomn!??0CFlexArray@@QEAA@HH@Z` at `0x18002b376`
- `wbemcomn!??1CFlexArray@@QEAA@XZ` at `0x18002b3dd`
- `wbemcomn!??1CFlexArray@@QEAA@XZ` at `0x18002b3dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMethodPart::CheckIds(CMethodPart *this, struct CWbemClass *a2, struct CWbemClass *a3)
{
  int Ids; // ebx
  int i; // ebx
  CMemoryLog *MemLogObject; // rax
  CWbemRefreshingSvc *v9; // rcx
  __int64 v10; // rdx
  CMemoryLog *v11; // rax
  __int64 v12; // r9
  CMemoryLog *v13; // rax
  _BYTE v14[96]; // [rsp+20h] [rbp-68h] BYREF

  CFlexArray::CFlexArray((CFlexArray *)v14, 8, 100);
  if ( a2 && (Ids = CWbemClass::GetIds(a2, (struct CFlexArray *)v14, 0), Ids < 0) )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, Ids);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 21;
LABEL_19:
      v12 = (unsigned int)Ids;
LABEL_24:
      WPP_SF_d(*((_QWORD *)v9 + 2), v10, WPP_fd56bafe8ef339ff81fc5cc004955919_Traceguids, v12);
    }
  }
  else if ( a3 && (Ids = CWbemClass::GetIds(a3, (struct CFlexArray *)v14, a2), Ids < 0) )
  {
    v11 = GetMemLogObject();
    CMemoryLog::Write(v11, Ids);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 22;
      goto LABEL_19;
    }
  }
  else
  {
    CFlexArray::Sort((CFlexArray *)v14);
    for ( i = 0; ; ++i )
    {
      if ( i >= CFlexArray::Size((CFlexArray *)v14) )
      {
        Ids = 0;
        goto LABEL_9;
      }
      if ( *(_DWORD *)CFlexArray::operator[](v14, (unsigned int)i) != i )
        break;
    }
    v13 = GetMemLogObject();
    Ids = -2147217352;
    CMemoryLog::Write(v13, -2147217352);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 23;
      v12 = 2147749944LL;
      goto LABEL_24;
    }
  }
LABEL_9:
  CFlexArray::~CFlexArray((CFlexArray *)v14);
  return (unsigned int)Ids;
}

```

## disassembly

```asm
0x18002b350  mov     [rsp+arg_0], rbx
0x18002b355  mov     [rsp+arg_8], rsi
0x18002b35a  push    rdi
0x18002b35b  sub     rsp, 80h
0x18002b362  mov     rdi, r8
0x18002b365  mov     rsi, rdx
0x18002b368  mov     edx, 8
0x18002b36d  lea     r8d, [rdx+5Ch]
0x18002b371  lea     rcx, [rsp+88h+var_68]
0x18002b376  call    cs:__imp_??0CFlexArray@@QEAA@HH@Z; CFlexArray::CFlexArray(int,int)
0x18002b37c  nop
0x18002b37d  test    rsi, rsi
0x18002b380  jnz     short loc_18002B3FA
0x18002b382  test    rdi, rdi
0x18002b385  jz      short loc_18002B3A1
0x18002b387  mov     r8, rsi; struct CWbemClass *
0x18002b38a  lea     rdx, [rsp+88h+var_68]; struct CFlexArray *
0x18002b38f  mov     rcx, rdi; this
0x18002b392  call    ?GetIds@CWbemClass@@QEAAJAEAVCFlexArray@@PEAV1@@Z; CWbemClass::GetIds(CFlexArray &,CWbemClass *)
0x18002b397  mov     ebx, eax
0x18002b399  test    eax, eax
0x18002b39b  js      loc_18002B44B
0x18002b3a1  lea     rcx, [rsp+88h+var_68]
0x18002b3a6  call    cs:__imp_?Sort@CFlexArray@@QEAAXXZ; CFlexArray::Sort(void)
0x18002b3ac  xor     ebx, ebx
0x18002b3ae  lea     rcx, [rsp+88h+var_68]
0x18002b3b3  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x18002b3b9  cmp     ebx, eax
0x18002b3bb  jge     short loc_18002B3D6
0x18002b3bd  mov     edx, ebx
0x18002b3bf  lea     rcx, [rsp+88h+var_68]
0x18002b3c4  call    cs:__imp_??ACFlexArray@@QEAAAEAPEAXH@Z; CFlexArray::operator[](int)
0x18002b3ca  cmp     [rax], ebx
0x18002b3cc  jnz     loc_18002B491
0x18002b3d2  inc     ebx
0x18002b3d4  jmp     short loc_18002B3AE
0x18002b3d6  xor     ebx, ebx
0x18002b3d8  lea     rcx, [rsp+88h+var_68]
0x18002b3dd  call    cs:__imp_??1CFlexArray@@QEAA@XZ; CFlexArray::~CFlexArray(void)
0x18002b3e3  mov     eax, ebx
0x18002b3e5  lea     r11, [rsp+88h+var_8]
0x18002b3ed  mov     rbx, [r11+10h]
0x18002b3f1  mov     rsi, [r11+18h]
0x18002b3f5  mov     rsp, r11
0x18002b3f8  pop     rdi
0x18002b3f9  retn
0x18002b3fa  xor     r8d, r8d; struct CWbemClass *
0x18002b3fd  lea     rdx, [rsp+88h+var_68]; struct CFlexArray *
0x18002b402  mov     rcx, rsi; this
0x18002b405  call    ?GetIds@CWbemClass@@QEAAJAEAVCFlexArray@@PEAV1@@Z; CWbemClass::GetIds(CFlexArray &,CWbemClass *)
0x18002b40a  mov     ebx, eax
0x18002b40c  test    eax, eax
0x18002b40e  jns     loc_18002B382
0x18002b414  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002b41a  mov     edx, ebx
0x18002b41c  mov     rcx, rax
0x18002b41f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002b425  lea     rax, WPP_GLOBAL_Control
0x18002b42c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b433  cmp     rcx, rax
0x18002b436  jz      short loc_18002B3D8
0x18002b438  test    byte ptr [rcx+1Ch], 1
0x18002b43c  jz      short loc_18002B3D8
0x18002b43e  cmp     byte ptr [rcx+19h], 2
0x18002b442  jb      short loc_18002B3D8
0x18002b444  mov     edx, 15h
0x18002b449  jmp     short loc_18002B48C
0x18002b44b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002b451  mov     edx, ebx
0x18002b453  mov     rcx, rax
0x18002b456  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002b45c  lea     rax, WPP_GLOBAL_Control
0x18002b463  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b46a  cmp     rcx, rax
0x18002b46d  jz      loc_18002B3D8
0x18002b473  test    byte ptr [rcx+1Ch], 1
0x18002b477  jz      loc_18002B3D8
0x18002b47d  cmp     byte ptr [rcx+19h], 2
0x18002b481  jb      loc_18002B3D8
0x18002b487  mov     edx, 16h
0x18002b48c  mov     r9d, ebx
0x18002b48f  jmp     short loc_18002B4DD
0x18002b491  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002b497  mov     ebx, 80041038h
0x18002b49c  mov     edx, ebx
0x18002b49e  mov     rcx, rax
0x18002b4a1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002b4a7  lea     rax, WPP_GLOBAL_Control
0x18002b4ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b4b5  cmp     rcx, rax
0x18002b4b8  jz      loc_18002B3D8
0x18002b4be  test    byte ptr [rcx+1Ch], 1
0x18002b4c2  jz      loc_18002B3D8
0x18002b4c8  cmp     byte ptr [rcx+19h], 2
0x18002b4cc  jb      loc_18002B3D8
0x18002b4d2  mov     edx, 17h
0x18002b4d7  mov     r9d, 80041038h
0x18002b4dd  lea     r8, WPP_fd56bafe8ef339ff81fc5cc004955919_Traceguids
0x18002b4e4  mov     rcx, [rcx+10h]
0x18002b4e8  call    WPP_SF_d
0x18002b4ed  jmp     loc_18002B3D8
```
