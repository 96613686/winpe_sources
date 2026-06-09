# CActiveXInstallBroker::ExtractFiles(ushort *,char const *,sSESSION *)

- ea: `0x1400048c0`
- end: `0x1400049b3`
- name: `?ExtractFiles@CActiveXInstallBroker@@QEAAJPEAGPEBDPEAUsSESSION@@@Z`
- size: `243`
- prototype: `__int64 __fastcall(CActiveXInstallBroker *__hidden this, unsigned __int16 *, const char *, struct sSESSION *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x140007df0`

## callees

- `0x1400048c0`
- `0x1400049bc`
- `0x14000b334`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x140004999`
- `KERNEL32!LeaveCriticalSection` at `0x140004999`
- `KERNEL32!EnterCriticalSection` at `0x1400048e7`
- `KERNEL32!EnterCriticalSection` at `0x1400048e7`
- `urlmon!Extract` at `0x140004958`
- `urlmon!Extract` at `0x140004958`

## pseudocode

```c
__int64 __fastcall CActiveXInstallBroker::ExtractFiles(
        CActiveXInstallBroker *this,
        unsigned __int16 *a2,
        const char *a3,
        struct sSESSION *a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  int IsAuthorized; // edi
  __int64 v10; // rdx
  int v11; // ecx
  int v12; // eax

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  if ( *(_DWORD *)this )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    if ( *((int *)this + 12) >= 3 )
    {
      if ( a2 && a3 && a4 && *((_QWORD *)a4 + 102) )
      {
        v10 = *((_QWORD *)this + 8) - (_QWORD)a2;
        do
        {
          v11 = *(unsigned __int16 *)((char *)a2 + v10);
          v12 = *a2 - v11;
          if ( v12 )
            break;
          ++a2;
        }
        while ( v11 );
        if ( v12 )
        {
          IsAuthorized = -2147024891;
        }
        else
        {
          IsAuthorized = CActiveXInstallBroker::FileIsAuthorized(this, a3);
          if ( IsAuthorized >= 0 )
          {
            IsAuthorized = Extract(a4, a3);
            if ( IsAuthorized >= 0 )
            {
              IsAuthorized = SetFileListIntegrityLevel(*((struct sFNAME **)this + 16));
              if ( IsAuthorized >= 0 )
                *((_DWORD *)this + 12) = 4;
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
      IsAuthorized = -2147019873;
    }
  }
  else
  {
    IsAuthorized = -2147024882;
  }
  if ( *(_DWORD *)this )
    LeaveCriticalSection(v4);
  return (unsigned int)IsAuthorized;
}

```

## disassembly

```asm
0x1400048c0  push    rbx
0x1400048c2  push    rbp
0x1400048c3  push    rsi
0x1400048c4  push    rdi
0x1400048c5  push    r14
0x1400048c7  sub     rsp, 20h
0x1400048cb  cmp     dword ptr [rcx], 0
0x1400048ce  lea     rbx, [rcx+8]
0x1400048d2  mov     rbp, r9
0x1400048d5  mov     r14, r8
0x1400048d8  mov     rdi, rdx
0x1400048db  mov     rsi, rcx
0x1400048de  jz      loc_14000498C
0x1400048e4  mov     rcx, rbx; lpCriticalSection
0x1400048e7  call    cs:__imp_EnterCriticalSection
0x1400048ee  nop     dword ptr [rax+rax+00h]
0x1400048f3  cmp     dword ptr [rsi+30h], 3
0x1400048f7  jge     short loc_140004903
0x1400048f9  mov     edi, 8007139Fh
0x1400048fe  jmp     loc_140004991
0x140004903  test    rdi, rdi
0x140004906  jz      short loc_140004985
0x140004908  test    r14, r14
0x14000490b  jz      short loc_140004985
0x14000490d  test    rbp, rbp
0x140004910  jz      short loc_140004985
0x140004912  cmp     qword ptr [rbp+330h], 0
0x14000491a  jz      short loc_140004985
0x14000491c  mov     rdx, [rsi+40h]
0x140004920  sub     rdx, rdi
0x140004923  movzx   eax, word ptr [rdi]
0x140004926  movzx   ecx, word ptr [rdi+rdx]
0x14000492a  sub     eax, ecx
0x14000492c  jnz     short loc_140004936
0x14000492e  add     rdi, 2
0x140004932  test    ecx, ecx
0x140004934  jnz     short loc_140004923
0x140004936  test    eax, eax
0x140004938  jz      short loc_140004941
0x14000493a  mov     edi, 80070005h
0x14000493f  jmp     short loc_140004991
0x140004941  mov     rdx, r14; char *
0x140004944  mov     rcx, rsi; this
0x140004947  call    ?FileIsAuthorized@CActiveXInstallBroker@@AEAAJPEBDH@Z; CActiveXInstallBroker::FileIsAuthorized(char const *,int)
0x14000494c  mov     edi, eax
0x14000494e  test    eax, eax
0x140004950  js      short loc_140004991
0x140004952  mov     rdx, r14
0x140004955  mov     rcx, rbp
0x140004958  call    cs:__imp_Extract
0x14000495f  nop     dword ptr [rax+rax+00h]
0x140004964  mov     edi, eax
0x140004966  test    eax, eax
0x140004968  js      short loc_140004991
0x14000496a  mov     rcx, [rsi+80h]; struct sFNAME *
0x140004971  call    ?SetFileListIntegrityLevel@@YAJPEAUsFNAME@@H@Z; SetFileListIntegrityLevel(sFNAME *,int)
0x140004976  mov     edi, eax
0x140004978  test    eax, eax
0x14000497a  js      short loc_140004991
0x14000497c  mov     dword ptr [rsi+30h], 4
0x140004983  jmp     short loc_140004991
0x140004985  mov     edi, 80070057h
0x14000498a  jmp     short loc_140004991
0x14000498c  mov     edi, 8007000Eh
0x140004991  cmp     dword ptr [rsi], 0
0x140004994  jz      short loc_1400049A5
0x140004996  mov     rcx, rbx; lpCriticalSection
0x140004999  call    cs:__imp_LeaveCriticalSection
0x1400049a0  nop     dword ptr [rax+rax+00h]
0x1400049a5  mov     eax, edi
0x1400049a7  add     rsp, 20h
0x1400049ab  pop     r14
0x1400049ad  pop     rdi
0x1400049ae  pop     rsi
0x1400049af  pop     rbp
0x1400049b0  pop     rbx
0x1400049b1  retn
```
