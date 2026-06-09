# CFileOwnerDialog::OwnerListThreadProc(void *)

- ea: `0x180014850`
- end: `0x180014977`
- name: `?OwnerListThreadProc@CFileOwnerDialog@@CAKPEAX@Z`
- size: `295`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180006eb4`
- `0x18001230c`
- `0x18001472c`
- `0x180014850`
- `0x18001ce34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800148e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800148e0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800148b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800148b5`
- `ntdll!NtClose` at `0x18001491a`
- `ntdll!NtClose` at `0x18001491a`
- `USER32!PostMessageW` at `0x18001492f`
- `USER32!PostMessageW` at `0x18001492f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CFileOwnerDialog::OwnerListThreadProc(char *Parameter, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v5; // rsi
  const unsigned __int16 *v6; // r12
  int v7; // r15d
  __int64 i; // r14
  struct IDiskQuotaUser *v9; // rbx
  unsigned int v11; // [rsp+20h] [rbp-58h]
  unsigned int v12; // [rsp+28h] [rbp-50h]
  unsigned int v13; // [rsp+30h] [rbp-48h]
  char pExceptionObject; // [rsp+80h] [rbp+8h] BYREF
  HANDLE Handle; // [rsp+88h] [rbp+10h] BYREF

  v5 = *((_QWORD *)Parameter + 9);
  v6 = (const unsigned __int16 *)**((_QWORD **)Parameter + 8);
  Handle = 0;
  if ( (int)CFileOwnerDialog::OpenNtObject((CFileOwnerDialog *)Parameter, v6, 0, a4, v11, v12, v13, &Handle) >= 0 )
  {
    v7 = *(_DWORD *)(v5 + 12);
    for ( i = 0; (int)i < v7; i = (unsigned int)(i + 1) )
    {
      if ( Parameter[153] )
        break;
      EnterCriticalSection((LPCRITICAL_SECTION)(v5 + 32));
      if ( (int)i >= *(_DWORD *)(v5 + 12) )
      {
        CMemoryException::CMemoryException(&pExceptionObject, 2);
        throw (CMemoryException *)&pExceptionObject;
      }
      v9 = *(struct IDiskQuotaUser **)(*(_QWORD *)(v5 + 24) + 8 * i);
      LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 32));
      CFileOwnerDialog::AddFilesToOwnerList(
        (CFileOwnerDialog *)Parameter,
        v6,
        Handle,
        v9,
        (struct COwnerList *)(Parameter + 80));
    }
  }
  if ( Handle )
    NtClose(Handle);
  PostMessageW(*((HWND *)Parameter + 2), 0x401u, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x180014850  mov     r11, rsp
0x180014853  mov     [r11+18h], rbx
0x180014857  mov     [r11+20h], rbp
0x18001485b  push    rsi
0x18001485c  push    rdi
0x18001485d  push    r12
0x18001485f  push    r14
0x180014861  push    r15
0x180014863  sub     rsp, 50h
0x180014867  mov     rdi, rcx
0x18001486a  mov     rsi, [rcx+48h]
0x18001486e  mov     rax, [rcx+40h]
0x180014872  mov     r12, [rax]
0x180014875  mov     qword ptr [r11+10h], 0
0x18001487d  lea     rax, [r11+10h]
0x180014881  mov     [r11-40h], rax
0x180014885  xor     r8d, r8d; void *
0x180014888  mov     rdx, r12; unsigned __int16 *
0x18001488b  call    ?OpenNtObject@CFileOwnerDialog@@AEAAJPEBGPEAXKKKKPEAPEAX@Z; CFileOwnerDialog::OpenNtObject(ushort const *,void *,ulong,ulong,ulong,ulong,void * *)
0x180014890  test    eax, eax
0x180014892  js      short loc_18001490D
0x180014894  mov     r15d, [rsi+0Ch]
0x180014898  xor     r14d, r14d
0x18001489b  test    r15d, r15d
0x18001489e  jle     short loc_18001490D
0x1800148a0  cmp     byte ptr [rdi+99h], 0
0x1800148a7  jnz     short loc_18001490D
0x1800148a9  lea     rbp, [rsi+20h]
0x1800148ad  mov     [rsp+78h+var_38], rbp
0x1800148b2  mov     rcx, rbp; lpCriticalSection
0x1800148b5  call    cs:__imp_EnterCriticalSection
0x1800148bb  mov     [rsp+78h+var_30], 1
0x1800148c3  cmp     r14d, [rsi+0Ch]
0x1800148c7  jge     loc_180014950
0x1800148cd  mov     rax, [rsi+18h]
0x1800148d1  mov     rbx, [rax+r14*8]
0x1800148d5  mov     [rsp+78h+var_30], 0
0x1800148dd  mov     rcx, rbp; lpCriticalSection
0x1800148e0  call    cs:__imp_LeaveCriticalSection
0x1800148e6  lea     rax, [rdi+50h]
0x1800148ea  mov     [rsp+78h+var_58], rax; struct COwnerList *
0x1800148ef  mov     r9, rbx; struct IDiskQuotaUser *
0x1800148f2  mov     r8, [rsp+78h+Handle]; void *
0x1800148fa  mov     rdx, r12; unsigned __int16 *
0x1800148fd  mov     rcx, rdi; this
0x180014900  call    ?AddFilesToOwnerList@CFileOwnerDialog@@AEAAJPEBGPEAXPEAUIDiskQuotaUser@@PEAVCOwnerList@@@Z; CFileOwnerDialog::AddFilesToOwnerList(ushort const *,void *,IDiskQuotaUser *,COwnerList *)
0x180014905  inc     r14d
0x180014908  cmp     r14d, r15d
0x18001490b  jl      short loc_1800148A0
0x18001490d  mov     rcx, [rsp+78h+Handle]; Handle
0x180014915  test    rcx, rcx
0x180014918  jz      short loc_180014920
0x18001491a  call    cs:__imp_NtClose
0x180014920  xor     r9d, r9d; lParam
0x180014923  xor     r8d, r8d; wParam
0x180014926  mov     edx, 401h; Msg
0x18001492b  mov     rcx, [rdi+10h]; hWnd
0x18001492f  call    cs:__imp_PostMessageW
0x180014935  xor     eax, eax
0x180014937  lea     r11, [rsp+78h+var_28]
0x18001493c  mov     rbx, [r11+40h]
0x180014940  mov     rbp, [r11+48h]
0x180014944  mov     rsp, r11
0x180014947  pop     r15
0x180014949  pop     r14
0x18001494b  pop     r12
0x18001494d  pop     rdi
0x18001494e  pop     rsi
0x18001494f  retn
0x180014950  mov     edx, 2
0x180014955  lea     rcx, [rsp+78h+pExceptionObject]
0x18001495d  call    ??0CMemoryException@@QEAA@W4reason@0@@Z; CMemoryException::CMemoryException(CMemoryException::reason)
0x180014962  lea     rdx, _TI2?AVCMemoryException@@; pThrowInfo
0x180014969  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180014971  call    _CxxThrowException_0
```
