# CActiveXInstallBroker::EnumerateFiles(ushort *,char const *,sSESSION *)

- ea: `0x140004738`
- end: `0x1400048b8`
- name: `?EnumerateFiles@CActiveXInstallBroker@@QEAAJPEAGPEBDPEAUsSESSION@@@Z`
- size: `384`
- prototype: `__int64 __fastcall(CActiveXInstallBroker *__hidden this, unsigned __int16 *, const char *, struct sSESSION *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x140007dc0`

## callees

- `0x140004738`
- `0x1400049bc`
- `0x140008684`
- `0x140008f78`
- `0x1400096b4`
- `0x14000b150`
- `0x14000b334`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14000489c`
- `KERNEL32!LeaveCriticalSection` at `0x14000489c`
- `KERNEL32!EnterCriticalSection` at `0x140004761`
- `KERNEL32!EnterCriticalSection` at `0x140004761`
- `ole32!CoTaskMemFree` at `0x140004831`
- `ole32!CoTaskMemFree` at `0x140004831`
- `urlmon!Extract` at `0x140004843`
- `urlmon!Extract` at `0x140004843`

## pseudocode

```c
__int64 __fastcall CActiveXInstallBroker::EnumerateFiles(
        CActiveXInstallBroker *this,
        unsigned __int16 *a2,
        const char *a3,
        struct sSESSION *a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  int v9; // r8d
  int IsAuthorized; // edi
  __int64 v11; // rdx
  int v12; // ecx
  int v13; // eax
  unsigned int v14; // edx
  __int64 v15; // rcx
  int v16; // edx
  LPVOID pv; // [rsp+60h] [rbp+8h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  if ( *(_DWORD *)this )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    if ( *((int *)this + 12) < 2 )
    {
      IsAuthorized = -2147019873;
      goto LABEL_24;
    }
    if ( a2 && a3 && a4 && !*((_QWORD *)a4 + 102) )
    {
      v11 = *((_QWORD *)this + 8) - (_QWORD)a2;
      do
      {
        v12 = *(unsigned __int16 *)((char *)a2 + v11);
        v13 = *a2 - v12;
        if ( v13 )
          break;
        ++a2;
      }
      while ( v12 );
      if ( v13 )
        goto LABEL_12;
      IsAuthorized = CActiveXInstallBroker::FileIsAuthorized(this, a3, v9);
      if ( IsAuthorized >= 0 )
      {
        IsAuthorized = CreateTempDir((char *)a4 + 32, v14);
        if ( IsAuthorized >= 0 )
        {
          pv = 0;
          IsAuthorized = SZtoWSZ(v15, (const char *)a4 + 32, (unsigned __int16 **)&pv);
          if ( IsAuthorized >= 0 )
          {
            if ( !*((_DWORD *)this + 35) && !(unsigned int)ContainingPathIsTamperProof((const unsigned __int16 *)pv) )
            {
LABEL_12:
              IsAuthorized = -2147024891;
              goto LABEL_24;
            }
            CoTaskMemFree(pv);
            IsAuthorized = Extract(a4, a3);
            if ( IsAuthorized >= 0 )
            {
              IsAuthorized = AddFilesToFileList(
                               (const char *)a4 + 32,
                               *((struct sFNAME **)a4 + 2),
                               (struct sFNAME **)this + 16);
              if ( IsAuthorized >= 0 )
              {
                IsAuthorized = SetFileListIntegrityLevel(*((struct sFNAME **)this + 16), v16);
                if ( IsAuthorized >= 0 )
                  *((_DWORD *)this + 12) = 3;
              }
            }
          }
        }
      }
    }
    else
    {
      IsAuthorized = -2147024809;
    }
  }
  else
  {
    IsAuthorized = -2147024882;
  }
LABEL_24:
  if ( *(_DWORD *)this )
    LeaveCriticalSection(v4);
  return (unsigned int)IsAuthorized;
}

```

## disassembly

```asm
0x140004738  push    rbx
0x14000473a  push    rbp
0x14000473b  push    rsi
0x14000473c  push    rdi
0x14000473d  push    r14
0x14000473f  push    r15
0x140004741  sub     rsp, 28h
0x140004745  cmp     dword ptr [rcx], 0
0x140004748  lea     rbx, [rcx+8]
0x14000474c  mov     rbp, r9
0x14000474f  mov     r15, r8
0x140004752  mov     rdi, rdx
0x140004755  mov     rsi, rcx
0x140004758  jz      loc_14000488F
0x14000475e  mov     rcx, rbx; lpCriticalSection
0x140004761  call    cs:__imp_EnterCriticalSection
0x140004768  nop     dword ptr [rax+rax+00h]
0x14000476d  cmp     dword ptr [rsi+30h], 2
0x140004771  jge     short loc_14000477D
0x140004773  mov     edi, 8007139Fh
0x140004778  jmp     loc_140004894
0x14000477d  test    rdi, rdi
0x140004780  jz      loc_140004888
0x140004786  test    r15, r15
0x140004789  jz      loc_140004888
0x14000478f  test    rbp, rbp
0x140004792  jz      loc_140004888
0x140004798  cmp     qword ptr [rbp+330h], 0
0x1400047a0  jnz     loc_140004888
0x1400047a6  mov     rdx, [rsi+40h]
0x1400047aa  sub     rdx, rdi
0x1400047ad  movzx   eax, word ptr [rdi]
0x1400047b0  movzx   ecx, word ptr [rdi+rdx]
0x1400047b4  sub     eax, ecx
0x1400047b6  jnz     short loc_1400047C0
0x1400047b8  add     rdi, 2
0x1400047bc  test    ecx, ecx
0x1400047be  jnz     short loc_1400047AD
0x1400047c0  test    eax, eax
0x1400047c2  jz      short loc_1400047CE
0x1400047c4  mov     edi, 80070005h
0x1400047c9  jmp     loc_140004894
0x1400047ce  mov     rdx, r15; char *
0x1400047d1  mov     rcx, rsi; this
0x1400047d4  call    ?FileIsAuthorized@CActiveXInstallBroker@@AEAAJPEBDH@Z; CActiveXInstallBroker::FileIsAuthorized(char const *,int)
0x1400047d9  mov     edi, eax
0x1400047db  test    eax, eax
0x1400047dd  js      loc_140004894
0x1400047e3  lea     r14, [rbp+20h]
0x1400047e7  mov     rcx, r14; char *
0x1400047ea  call    ?CreateTempDir@@YAJPEADK@Z; CreateTempDir(char *,ulong)
0x1400047ef  mov     edi, eax
0x1400047f1  test    eax, eax
0x1400047f3  js      loc_140004894
0x1400047f9  lea     r8, [rsp+58h+pv]; unsigned __int16 **
0x1400047fe  mov     [rsp+58h+pv], 0
0x140004807  mov     rdx, r14; char *
0x14000480a  call    ?SZtoWSZ@@YAJIPEBDPEAPEAG@Z; SZtoWSZ(uint,char const *,ushort * *)
0x14000480f  mov     edi, eax
0x140004811  test    eax, eax
0x140004813  js      short loc_140004894
0x140004815  cmp     dword ptr [rsi+8Ch], 0
0x14000481c  jnz     short loc_14000482C
0x14000481e  mov     rcx, [rsp+58h+pv]; unsigned __int16 *
0x140004823  call    ?ContainingPathIsTamperProof@@YAHPEBG@Z; ContainingPathIsTamperProof(ushort const *)
0x140004828  test    eax, eax
0x14000482a  jz      short loc_1400047C4
0x14000482c  mov     rcx, [rsp+58h+pv]; pv
0x140004831  call    cs:__imp_CoTaskMemFree
0x140004838  nop     dword ptr [rax+rax+00h]
0x14000483d  mov     rdx, r15
0x140004840  mov     rcx, rbp
0x140004843  call    cs:__imp_Extract
0x14000484a  nop     dword ptr [rax+rax+00h]
0x14000484f  mov     edi, eax
0x140004851  test    eax, eax
0x140004853  js      short loc_140004894
0x140004855  mov     rdx, [rbp+10h]; struct sFNAME *
0x140004859  lea     r15, [rsi+80h]
0x140004860  mov     r8, r15; struct sFNAME **
0x140004863  mov     rcx, r14; char *
0x140004866  call    ?AddFilesToFileList@@YAJPEBDPEAUsFNAME@@PEAPEAU1@@Z; AddFilesToFileList(char const *,sFNAME *,sFNAME * *)
0x14000486b  mov     edi, eax
0x14000486d  test    eax, eax
0x14000486f  js      short loc_140004894
0x140004871  mov     rcx, [r15]; struct sFNAME *
0x140004874  call    ?SetFileListIntegrityLevel@@YAJPEAUsFNAME@@H@Z; SetFileListIntegrityLevel(sFNAME *,int)
0x140004879  mov     edi, eax
0x14000487b  test    eax, eax
0x14000487d  js      short loc_140004894
0x14000487f  mov     dword ptr [rsi+30h], 3
0x140004886  jmp     short loc_140004894
0x140004888  mov     edi, 80070057h
0x14000488d  jmp     short loc_140004894
0x14000488f  mov     edi, 8007000Eh
0x140004894  cmp     dword ptr [rsi], 0
0x140004897  jz      short loc_1400048A8
0x140004899  mov     rcx, rbx; lpCriticalSection
0x14000489c  call    cs:__imp_LeaveCriticalSection
0x1400048a3  nop     dword ptr [rax+rax+00h]
0x1400048a8  mov     eax, edi
0x1400048aa  add     rsp, 28h
0x1400048ae  pop     r15
0x1400048b0  pop     r14
0x1400048b2  pop     rdi
0x1400048b3  pop     rsi
0x1400048b4  pop     rbp
0x1400048b5  pop     rbx
0x1400048b6  retn
```
