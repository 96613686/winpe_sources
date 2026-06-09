# CWbemObject::GetKeyString(long,ushort * *)

- ea: `0x18007d8f0`
- end: `0x18007daa2`
- name: `?GetKeyString@CWbemObject@@UEAAJJPEAPEAG@Z`
- size: `434`
- prototype: `__int64 __fastcall(CWbemObject *__hidden this, int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180037120`
- `0x18004cc70`
- `0x180050490`
- `0x18005f8cc`
- `0x180078480`
- `0x18007d8f0`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18007d97d`
- `wbemcomn!GetMemLogObject` at `0x18007d9d7`
- `wbemcomn!GetMemLogObject` at `0x18007da36`
- `wbemcomn!GetMemLogObject` at `0x18007d97d`
- `wbemcomn!GetMemLogObject` at `0x18007d9d7`
- `wbemcomn!GetMemLogObject` at `0x18007da36`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007d988`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007d9e7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007da46`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007d988`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007d9e7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007da46`
- `OLEAUT32!__imp_SysAllocString` at `0x18007d952`
- `OLEAUT32!__imp_SysAllocString` at `0x18007d952`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWbemObject::GetKeyString(CWbemObject *this, int a2, unsigned __int16 **a3)
{
  unsigned __int16 *KeyStr; // rax
  unsigned __int16 *v6; // rax
  int v7; // ebx
  CMemoryLog *v8; // rax
  __int64 result; // rax
  CMemoryLog *v10; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v12; // rax
  CMemoryLog *v13; // rax
  void *v14[3]; // [rsp+20h] [rbp-18h] BYREF
  char v15; // [rsp+58h] [rbp+20h] BYREF

  try
  {
    if ( a2 || !a3 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -2147217400);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          248,
          WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids,
          2147749896LL);
      }
      result = 2147749896LL;
    }
    else
    {
      CWbemObject::CLock::CLock((CWbemObject::CLock *)&v15, this, 0);
      if ( (**((_BYTE **)this + 9) & 3) == 2 )
      {
        KeyStr = CWbemInstance::GetKeyStr(this);
        v14[0] = KeyStr;
        v14[1] = 0;
        if ( KeyStr )
        {
          v6 = SysAllocString(KeyStr);
          *a3 = v6;
          v7 = -2147217402;
          if ( v6 )
            v7 = 0;
        }
        else
        {
          v7 = -2147217386;
        }
        CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v14);
        if ( v7 < 0 )
        {
          v8 = GetMemLogObject();
          CMemoryLog::Write(v8, v7);
        }
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            250,
            WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids,
            (unsigned int)v7);
        }
        CWbemObject::CLock::~CLock((CWbemObject::CLock *)&v15);
        result = (unsigned int)v7;
      }
      else
      {
        v10 = GetMemLogObject();
        CMemoryLog::Write(v10, -2147217386);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            249,
            WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids,
            2147749910LL);
        }
        CWbemObject::CLock::~CLock((CWbemObject::CLock *)&v15);
        result = 2147749910LL;
      }
    }
  }
  catch ( CX_MemoryException )
  {
    v12 = GetMemLogObject();
    CMemoryLog::Write(v12, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 251, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  catch ( CX_Exception )
  {
    v13 = GetMemLogObject();
    CMemoryLog::Write(v13, -2147217398);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 252, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids, 2147749898LL);
    }
    return 2147749898LL;
  }
  return result;
}

```

## disassembly

```asm
0x18007d8f0  mov     [rsp+arg_0], rbx
0x18007d8f5  push    rdi
0x18007d8f6  sub     rsp, 30h
0x18007d8fa  mov     rdi, r8
0x18007d8fd  mov     rbx, rcx
0x18007d900  test    edx, edx
0x18007d902  jnz     loc_18007DA36
0x18007d908  test    r8, r8
0x18007d90b  jz      loc_18007DA36
0x18007d911  xor     r8d, r8d; int
0x18007d914  mov     rdx, rcx; struct CWbemObject *
0x18007d917  lea     rcx, [rsp+38h+arg_18]; this
0x18007d91c  call    ??0CLock@CWbemObject@@QEAA@PEAV1@J@Z; CWbemObject::CLock::CLock(CWbemObject *,long)
0x18007d921  nop
0x18007d922  mov     rax, [rbx+48h]
0x18007d926  mov     cl, [rax]
0x18007d928  and     cl, 3
0x18007d92b  cmp     cl, 2
0x18007d92e  jnz     loc_18007D9D7
0x18007d934  mov     rcx, rbx; this
0x18007d937  call    ?GetKeyStr@CWbemInstance@@QEAAPEAGXZ; CWbemInstance::GetKeyStr(void)
0x18007d93c  mov     [rsp+38h+var_18], rax
0x18007d941  mov     [rsp+38h+var_10], 0
0x18007d94a  test    rax, rax
0x18007d94d  jz      short loc_18007D96A
0x18007d94f  mov     rcx, rax; psz
0x18007d952  call    cs:__imp_SysAllocString
0x18007d958  mov     [rdi], rax
0x18007d95b  mov     ebx, 80041006h
0x18007d960  xor     ecx, ecx
0x18007d962  test    rax, rax
0x18007d965  cmovnz  ebx, ecx
0x18007d968  jmp     short loc_18007D96F
0x18007d96a  mov     ebx, 80041016h
0x18007d96f  lea     rcx, [rsp+38h+var_18]
0x18007d974  call    ??1?$CVectorDeleteMe@G@@QEAA@XZ; CVectorDeleteMe<ushort>::~CVectorDeleteMe<ushort>(void)
0x18007d979  test    ebx, ebx
0x18007d97b  jns     short loc_18007D98E
0x18007d97d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007d983  mov     edx, ebx
0x18007d985  mov     rcx, rax
0x18007d988  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007d98e  lea     rax, WPP_GLOBAL_Control
0x18007d995  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d99c  cmp     rcx, rax
0x18007d99f  jz      short loc_18007D9C6
0x18007d9a1  test    byte ptr [rcx+1Ch], 1
0x18007d9a5  jz      short loc_18007D9C6
0x18007d9a7  cmp     byte ptr [rcx+19h], 2
0x18007d9ab  jb      short loc_18007D9C6
0x18007d9ad  mov     edx, 0FAh
0x18007d9b2  mov     r9d, ebx
0x18007d9b5  lea     r8, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids
0x18007d9bc  mov     rcx, [rcx+10h]
0x18007d9c0  call    WPP_SF_d
0x18007d9c5  nop
0x18007d9c6  lea     rcx, [rsp+38h+arg_18]; this
0x18007d9cb  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x18007d9d0  mov     eax, ebx
0x18007d9d2  jmp     loc_18007DA96
0x18007d9d7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007d9dd  mov     ebx, 80041016h
0x18007d9e2  mov     edx, ebx
0x18007d9e4  mov     rcx, rax
0x18007d9e7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007d9ed  lea     rax, WPP_GLOBAL_Control
0x18007d9f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d9fb  cmp     rcx, rax
0x18007d9fe  jz      short loc_18007DA28
0x18007da00  test    byte ptr [rcx+1Ch], 1
0x18007da04  jz      short loc_18007DA28
0x18007da06  cmp     byte ptr [rcx+19h], 2
0x18007da0a  jb      short loc_18007DA28
0x18007da0c  mov     edx, 0F9h
0x18007da11  mov     r9d, 80041016h
0x18007da17  lea     r8, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids
0x18007da1e  mov     rcx, [rcx+10h]
0x18007da22  call    WPP_SF_d
0x18007da27  nop
0x18007da28  lea     rcx, [rsp+38h+arg_18]; this
0x18007da2d  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x18007da32  mov     eax, ebx
0x18007da34  jmp     short loc_18007DA96
0x18007da36  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007da3c  mov     ebx, 80041008h
0x18007da41  mov     edx, ebx
0x18007da43  mov     rcx, rax
0x18007da46  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007da4c  lea     rax, WPP_GLOBAL_Control
0x18007da53  mov     rcx, cs:WPP_GLOBAL_Control
0x18007da5a  cmp     rcx, rax
0x18007da5d  jz      short loc_18007DA86
0x18007da5f  test    byte ptr [rcx+1Ch], 1
0x18007da63  jz      short loc_18007DA86
0x18007da65  cmp     byte ptr [rcx+19h], 2
0x18007da69  jb      short loc_18007DA86
0x18007da6b  mov     edx, 0F8h
0x18007da70  mov     r9d, 80041008h
0x18007da76  lea     r8, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids
0x18007da7d  mov     rcx, [rcx+10h]
0x18007da81  call    WPP_SF_d
0x18007da86  mov     eax, ebx
0x18007da88  jmp     short loc_18007DA96
0x18007da8a  mov     eax, 80041006h
0x18007da8f  jmp     short loc_18007DA96
0x18007da91  mov     eax, 8004100Ah
0x18007da96  mov     rbx, [rsp+38h+arg_0]
0x18007da9b  add     rsp, 30h
0x18007da9f  pop     rdi
0x18007daa0  retn
```
