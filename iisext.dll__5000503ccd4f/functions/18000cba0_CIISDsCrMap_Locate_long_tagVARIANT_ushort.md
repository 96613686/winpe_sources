# CIISDsCrMap::Locate(long,tagVARIANT,ushort *)

- ea: `0x18000cba0`
- end: `0x18000cdd2`
- name: `?Locate@CIISDsCrMap@@QEAAJJUtagVARIANT@@PEAG@Z`
- size: `562`
- prototype: `__int64 __fastcall(CIISDsCrMap *__hidden this, int, struct tagVARIANT *__struct_ptr, unsigned __int16 *)`
- caller_count: `9`
- callee_count: `6`
- tags: ``

## callers

- `0x18000b22c`
- `0x18000b6b0`
- `0x18000b7a8`
- `0x18000bd80`
- `0x18000c0ac`
- `0x18000d4c0`
- `0x18000d5dc`
- `0x18000d81c`
- `0x18000d930`

## callees

- `0x18000c460`
- `0x18000c5ec`
- `0x18000cba0`
- `0x18000cdd8`
- `0x18000d6d8`
- `0x1800111e0`

## import_xrefs

- `msvcrt!swprintf_s` at `0x18000ccc2`
- `msvcrt!swprintf_s` at `0x18000cd7f`
- `msvcrt!swprintf_s` at `0x18000ccc2`
- `msvcrt!swprintf_s` at `0x18000cd7f`
- `KERNEL32!LocalFree` at `0x18000cd8f`
- `KERNEL32!LocalFree` at `0x18000cda4`
- `KERNEL32!LocalFree` at `0x18000cd8f`
- `KERNEL32!LocalFree` at `0x18000cda4`
- `KERNEL32!MultiByteToWideChar` at `0x18000cc93`
- `KERNEL32!MultiByteToWideChar` at `0x18000cc93`

## pseudocode

```c
__int64 __fastcall CIISDsCrMap::Locate(CIISDsCrMap *this, int a2, struct tagVARIANT *a3, unsigned __int16 *a4)
{
  IRecordInfo *pRecInfo; // xmm1_8
  int v8; // r9d
  int v9; // edx
  int v10; // edx
  int v11; // edx
  int StringFromVariant; // ebx
  CHAR *v13; // rdi
  int v14; // eax
  unsigned int v15; // esi
  HLOCAL v16; // rsi
  int cbMultiByte; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v18; // [rsp+34h] [rbp-CCh] BYREF
  LPCCH lpMultiByteStr; // [rsp+38h] [rbp-C8h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-C0h] BYREF
  struct tagVARIANT v21; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR WideCharStr[264]; // [rsp+70h] [rbp-90h] BYREF

  if ( *((_DWORD *)this + 35) )
  {
    pRecInfo = a3->pRecInfo;
    *(_OWORD *)&v21.vt = *(_OWORD *)&a3->vt;
    v21.pRecInfo = pRecInfo;
    return CIISDsCrMap::LocateIIS6(this, a2, &v21, a4);
  }
  v8 = 1;
  lpMultiByteStr = 0;
  cbMultiByte = 0;
  hMem = 0;
  v18 = 0;
  v9 = a2 - 1;
  if ( !v9 )
  {
    v15 = 2073;
    v8 = 0;
LABEL_16:
    StringFromVariant = GetStringFromVariant(a3, (char **)&lpMultiByteStr, (unsigned int *)&cbMultiByte, v8);
    if ( StringFromVariant >= 0 )
    {
      v13 = (CHAR *)lpMultiByteStr;
      StringFromVariant = CIISDsCrMap::SetMdData(
                            this,
                            (unsigned __int16 *)&::hMem,
                            v15,
                            3,
                            cbMultiByte,
                            (unsigned __int8 *)lpMultiByteStr);
      if ( StringFromVariant >= 0 )
      {
        StringFromVariant = CIISDsCrMap::GetMdData(
                              this,
                              (unsigned __int16 *)&::hMem,
                              v15,
                              1u,
                              &v18,
                              (unsigned __int8 **)&hMem);
        if ( StringFromVariant >= 0 )
        {
          v16 = hMem;
          if ( v18 == 4 )
            swprintf_s(a4, 0x101u, L"mappings/%u", *(unsigned int *)hMem);
          else
            StringFromVariant = -2147467259;
          LocalFree(v16);
        }
      }
      goto LABEL_24;
    }
    goto LABEL_23;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    v15 = 2074;
    goto LABEL_16;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
    v15 = 2072;
    goto LABEL_16;
  }
  if ( v11 == 1 )
  {
    StringFromVariant = GetStringFromVariant(a3, (char **)&lpMultiByteStr, (unsigned int *)&cbMultiByte, 1);
    if ( StringFromVariant >= 0 )
    {
      v13 = (CHAR *)lpMultiByteStr;
      v14 = MultiByteToWideChar(0, 0, lpMultiByteStr, cbMultiByte, WideCharStr, 257);
      if ( v14 && v14 < 248 )
        swprintf_s(a4, 0x101u, L"mappings/%s", WideCharStr);
      else
        StringFromVariant = -2147467259;
      goto LABEL_24;
    }
LABEL_23:
    v13 = (CHAR *)lpMultiByteStr;
LABEL_24:
    if ( v13 )
      LocalFree(v13);
    return (unsigned int)StringFromVariant;
  }
  return (unsigned int)-2147467259;
}

```

## disassembly

```asm
0x18000cba0  mov     [rsp-8+arg_8], rbx
0x18000cba5  push    rbp
0x18000cba6  push    rsi
0x18000cba7  push    rdi
0x18000cba8  push    r14
0x18000cbaa  push    r15
0x18000cbac  lea     rbp, [rsp-190h]
0x18000cbb4  sub     rsp, 290h
0x18000cbbb  mov     rax, cs:__security_cookie
0x18000cbc2  xor     rax, rsp
0x18000cbc5  mov     [rbp+1B0h+var_30], rax
0x18000cbcc  cmp     dword ptr [rcx+8Ch], 0
0x18000cbd3  mov     r15, r9
0x18000cbd6  mov     r10, r8
0x18000cbd9  mov     r14, rcx
0x18000cbdc  jz      short loc_18000CC02
0x18000cbde  movaps  xmm0, xmmword ptr [r8]
0x18000cbe2  movsd   xmm1, qword ptr [r8+10h]
0x18000cbe8  lea     r8, [rsp+2B0h+var_260]; struct tagVARIANT
0x18000cbed  movaps  xmmword ptr [rsp+2B0h+var_260], xmm0
0x18000cbf2  movsd   qword ptr [rsp+2B0h+var_260+10h], xmm1
0x18000cbf8  call    ?LocateIIS6@CIISDsCrMap@@AEAAJJUtagVARIANT@@PEAG@Z; CIISDsCrMap::LocateIIS6(long,tagVARIANT,ushort *)
0x18000cbfd  jmp     loc_18000CDAC
0x18000cc02  mov     r9d, 1; int
0x18000cc08  mov     [rsp+2B0h+lpMultiByteStr], 0
0x18000cc11  mov     [rsp+2B0h+cbMultiByte], 0
0x18000cc19  mov     [rsp+2B0h+hMem], 0
0x18000cc22  mov     [rsp+2B0h+var_27C], 0
0x18000cc2a  sub     edx, r9d
0x18000cc2d  jz      loc_18000CCDB
0x18000cc33  sub     edx, r9d
0x18000cc36  jz      loc_18000CCD4
0x18000cc3c  sub     edx, r9d
0x18000cc3f  jz      loc_18000CCCD
0x18000cc45  cmp     edx, r9d
0x18000cc48  jz      short loc_18000CC54
0x18000cc4a  mov     ebx, 80004005h
0x18000cc4f  jmp     loc_18000CDAA
0x18000cc54  lea     r8, [rsp+2B0h+cbMultiByte]; unsigned int *
0x18000cc59  mov     rcx, r10; pvargSrc
0x18000cc5c  lea     rdx, [rsp+2B0h+lpMultiByteStr]; char **
0x18000cc61  call    ?GetStringFromVariant@@YAJPEAUtagVARIANT@@PEAPEADPEAKH@Z; GetStringFromVariant(tagVARIANT *,char * *,ulong *,int)
0x18000cc66  mov     ebx, eax
0x18000cc68  test    eax, eax
0x18000cc6a  js      loc_18000CD97
0x18000cc70  mov     rdi, [rsp+2B0h+lpMultiByteStr]
0x18000cc75  lea     rax, [rsp+2B0h+WideCharStr]
0x18000cc7a  mov     r9d, [rsp+2B0h+cbMultiByte]; cbMultiByte
0x18000cc7f  mov     r8, rdi; lpMultiByteStr
0x18000cc82  mov     [rsp+2B0h+cchWideChar], 101h; cchWideChar
0x18000cc8a  xor     edx, edx; dwFlags
0x18000cc8c  xor     ecx, ecx; CodePage
0x18000cc8e  mov     [rsp+2B0h+lpWideCharStr], rax; lpWideCharStr
0x18000cc93  call    cs:__imp_MultiByteToWideChar
0x18000cc99  test    eax, eax
0x18000cc9b  jnz     short loc_18000CCA7
0x18000cc9d  mov     ebx, 80004005h
0x18000cca2  jmp     loc_18000CD9C
0x18000cca7  cmp     eax, 0F8h
0x18000ccac  jge     short loc_18000CC9D
0x18000ccae  lea     r9, [rsp+2B0h+WideCharStr]
0x18000ccb3  mov     edx, 101h; BufferCount
0x18000ccb8  lea     r8, aMappingsS; "mappings/%s"
0x18000ccbf  mov     rcx, r15; Buffer
0x18000ccc2  call    cs:__imp_swprintf_s
0x18000ccc8  jmp     loc_18000CD9C
0x18000cccd  mov     esi, 818h
0x18000ccd2  jmp     short loc_18000CCE3
0x18000ccd4  mov     esi, 81Ah
0x18000ccd9  jmp     short loc_18000CCE3
0x18000ccdb  mov     esi, 819h
0x18000cce0  xor     r9d, r9d; int
0x18000cce3  lea     r8, [rsp+2B0h+cbMultiByte]; unsigned int *
0x18000cce8  mov     rcx, r10; pvargSrc
0x18000cceb  lea     rdx, [rsp+2B0h+lpMultiByteStr]; char **
0x18000ccf0  call    ?GetStringFromVariant@@YAJPEAUtagVARIANT@@PEAPEADPEAKH@Z; GetStringFromVariant(tagVARIANT *,char * *,ulong *,int)
0x18000ccf5  mov     ebx, eax
0x18000ccf7  test    eax, eax
0x18000ccf9  js      loc_18000CD97
0x18000ccff  mov     eax, [rsp+2B0h+cbMultiByte]
0x18000cd03  lea     rdx, hMem; unsigned __int16 *
0x18000cd0a  mov     rdi, [rsp+2B0h+lpMultiByteStr]
0x18000cd0f  mov     r9d, 3; unsigned int
0x18000cd15  mov     qword ptr [rsp+2B0h+cchWideChar], rdi; unsigned __int8 *
0x18000cd1a  mov     r8d, esi; unsigned int
0x18000cd1d  mov     rcx, r14; this
0x18000cd20  mov     dword ptr [rsp+2B0h+lpWideCharStr], eax; unsigned int
0x18000cd24  call    ?SetMdData@CIISDsCrMap@@QEAAJPEAGKKKPEAE@Z; CIISDsCrMap::SetMdData(ushort *,ulong,ulong,ulong,uchar *)
0x18000cd29  mov     ebx, eax
0x18000cd2b  test    eax, eax
0x18000cd2d  js      short loc_18000CD9C
0x18000cd2f  lea     rax, [rsp+2B0h+hMem]
0x18000cd34  mov     r9d, 1; unsigned int
0x18000cd3a  mov     qword ptr [rsp+2B0h+cchWideChar], rax; unsigned __int8 **
0x18000cd3f  lea     rdx, hMem; unsigned __int16 *
0x18000cd46  lea     rax, [rsp+2B0h+var_27C]
0x18000cd4b  mov     r8d, esi; unsigned int
0x18000cd4e  mov     rcx, r14; this
0x18000cd51  mov     [rsp+2B0h+lpWideCharStr], rax; unsigned int *
0x18000cd56  call    ?GetMdData@CIISDsCrMap@@QEAAJPEAGKKPEAKPEAPEAE@Z; CIISDsCrMap::GetMdData(ushort *,ulong,ulong,ulong *,uchar * *)
0x18000cd5b  mov     ebx, eax
0x18000cd5d  test    eax, eax
0x18000cd5f  js      short loc_18000CD9C
0x18000cd61  cmp     [rsp+2B0h+var_27C], 4
0x18000cd66  mov     rsi, [rsp+2B0h+hMem]
0x18000cd6b  jnz     short loc_18000CD87
0x18000cd6d  mov     r9d, [rsi]
0x18000cd70  lea     r8, aMappingsU; "mappings/%u"
0x18000cd77  mov     edx, 101h; BufferCount
0x18000cd7c  mov     rcx, r15; Buffer
0x18000cd7f  call    cs:__imp_swprintf_s
0x18000cd85  jmp     short loc_18000CD8C
0x18000cd87  mov     ebx, 80004005h
0x18000cd8c  mov     rcx, rsi; hMem
0x18000cd8f  call    cs:__imp_LocalFree
0x18000cd95  jmp     short loc_18000CD9C
0x18000cd97  mov     rdi, [rsp+2B0h+lpMultiByteStr]
0x18000cd9c  test    rdi, rdi
0x18000cd9f  jz      short loc_18000CDAA
0x18000cda1  mov     rcx, rdi; hMem
0x18000cda4  call    cs:__imp_LocalFree
0x18000cdaa  mov     eax, ebx
0x18000cdac  mov     rcx, [rbp+1B0h+var_30]
0x18000cdb3  xor     rcx, rsp; StackCookie
0x18000cdb6  call    __security_check_cookie
0x18000cdbb  mov     rbx, [rsp+2B0h+arg_8]
0x18000cdc3  add     rsp, 290h
0x18000cdca  pop     r15
0x18000cdcc  pop     r14
0x18000cdce  pop     rdi
0x18000cdcf  pop     rsi
0x18000cdd0  pop     rbp
0x18000cdd1  retn
```
