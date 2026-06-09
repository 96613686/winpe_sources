# CMDCOM::ComMDAddMetaObjectD(ulong,uchar *,int)

- ea: `0x180015c50`
- end: `0x180015d5c`
- name: `?ComMDAddMetaObjectD@CMDCOM@@QEAAJKPEAEH@Z`
- size: `268`
- prototype: `int(CMDCOM *__hidden this, unsigned int, unsigned __int8 *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180015c40`
- `0x180015d70`

## callees

- `0x180002d60`
- `0x180005690`
- `0x180015c50`
- `0x18001a0d0`
- `0x18001aeb4`
- `0x18001da80`
- `0x1800309d0`

## import_xrefs

- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180015d25`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180015d25`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180015cd3`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180015cd3`

## pseudocode

```c
__int64 __fastcall CMDCOM::ComMDAddMetaObjectD(CMDCOM *this, unsigned int a2, char *a3, int a4)
{
  int v7; // ebx
  struct CMDHandle *HandleObject; // rax
  struct CMDHandle *v9; // rbp
  char *v11[2]; // [rsp+20h] [rbp-238h] BYREF
  char v12[512]; // [rsp+30h] [rbp-228h] BYREF

  if ( g_dwInitialized )
  {
    v11[0] = a3;
    if ( a3 && (SkipPathDelimeter(v11, a4), v11[0]) && ExtractNameFromPath(v11, v12, a4) >= 0 )
    {
      CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)&g_LockMasterResource);
      HandleObject = GetHandleObject(a2);
      v9 = HandleObject;
      if ( HandleObject )
      {
        v7 = AddObjectToDataBase(a2, HandleObject, a3, a4);
        if ( v7 >= 0 )
        {
          ++*(_DWORD *)&g_dwSystemChangeNumber;
          INCREMENT_SCHEMA_CHANGE_NUMBER(a2, v9, a3, a4);
        }
      }
      else
      {
        v7 = -2147024890;
      }
      CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)&g_LockMasterResource);
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  else
  {
    return (unsigned int)-2146646016;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180015c50  mov     [rsp+arg_0], rbx
0x180015c55  mov     [rsp+arg_18], rbp
0x180015c5a  push    rsi
0x180015c5b  push    rdi
0x180015c5c  push    r14
0x180015c5e  sub     rsp, 240h
0x180015c65  mov     rax, cs:__security_cookie
0x180015c6c  xor     rax, rsp
0x180015c6f  mov     [rsp+258h+var_28], rax
0x180015c77  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x180015c7d  mov     esi, r9d
0x180015c80  mov     rdi, r8
0x180015c83  mov     r14d, edx
0x180015c86  test    eax, eax
0x180015c88  jnz     short loc_180015C94
0x180015c8a  mov     ebx, 800CC800h
0x180015c8f  jmp     loc_180015D32
0x180015c94  mov     [rsp+258h+var_238], rdi
0x180015c99  test    rdi, rdi
0x180015c9c  jz      loc_180015D2D
0x180015ca2  mov     edx, esi; int
0x180015ca4  lea     rcx, [rsp+258h+var_238]; char **
0x180015ca9  call    ?SkipPathDelimeter@@YAXAEAPEADH@Z; SkipPathDelimeter(char * &,int)
0x180015cae  cmp     [rsp+258h+var_238], 0
0x180015cb4  jz      short loc_180015D2D
0x180015cb6  mov     r8d, esi; int
0x180015cb9  lea     rdx, [rsp+258h+var_228]; char *
0x180015cbe  lea     rcx, [rsp+258h+var_238]; char **
0x180015cc3  call    ?ExtractNameFromPath@@YAJAEAPEADPEADH@Z; ExtractNameFromPath(char * &,char *,int)
0x180015cc8  test    eax, eax
0x180015cca  js      short loc_180015D2D
0x180015ccc  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180015cd3  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180015cd9  mov     ecx, r14d; unsigned int
0x180015cdc  call    ?GetHandleObject@@YAPEAVCMDHandle@@K@Z; GetHandleObject(ulong)
0x180015ce1  mov     rbp, rax
0x180015ce4  test    rax, rax
0x180015ce7  jz      short loc_180015D19
0x180015ce9  mov     r9d, esi; int
0x180015cec  mov     r8, rdi; char *
0x180015cef  mov     rdx, rax; struct CMDHandle *
0x180015cf2  mov     ecx, r14d; unsigned int
0x180015cf5  call    ?AddObjectToDataBase@@YAJKPEAVCMDHandle@@PEADH@Z; AddObjectToDataBase(ulong,CMDHandle *,char *,int)
0x180015cfa  mov     ebx, eax
0x180015cfc  test    eax, eax
0x180015cfe  js      short loc_180015D1E
0x180015d00  inc     cs:?g_dwSystemChangeNumber@@3KA; ulong g_dwSystemChangeNumber
0x180015d06  mov     r9d, esi; int
0x180015d09  mov     r8, rdi; char *
0x180015d0c  mov     rdx, rbp; struct CMDHandle *
0x180015d0f  mov     ecx, r14d; unsigned int
0x180015d12  call    ?INCREMENT_SCHEMA_CHANGE_NUMBER@@YAXKPEAVCMDHandle@@PEADH@Z; INCREMENT_SCHEMA_CHANGE_NUMBER(ulong,CMDHandle *,char *,int)
0x180015d17  jmp     short loc_180015D1E
0x180015d19  mov     ebx, 80070006h
0x180015d1e  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180015d25  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180015d2b  jmp     short loc_180015D32
0x180015d2d  mov     ebx, 80070057h
0x180015d32  mov     eax, ebx
0x180015d34  mov     rcx, [rsp+258h+var_28]
0x180015d3c  xor     rcx, rsp; StackCookie
0x180015d3f  call    __security_check_cookie
0x180015d44  lea     r11, [rsp+258h+var_18]
0x180015d4c  mov     rbx, [r11+20h]
0x180015d50  mov     rbp, [r11+38h]
0x180015d54  mov     rsp, r11
0x180015d57  pop     r14
0x180015d59  pop     rdi
0x180015d5a  pop     rsi
0x180015d5b  retn
```
