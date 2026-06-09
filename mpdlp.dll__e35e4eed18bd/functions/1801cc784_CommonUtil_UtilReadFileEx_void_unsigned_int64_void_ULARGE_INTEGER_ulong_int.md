# CommonUtil::UtilReadFileEx(void *,unsigned __int64 *,void *,_ULARGE_INTEGER *,ulong,int)

- ea: `0x1801cc784`
- end: `0x1801ccaf0`
- name: `?UtilReadFileEx@CommonUtil@@YAJPEAXPEA_K0PEAT_ULARGE_INTEGER@@KH@Z`
- size: `876`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, void *, unsigned __int64 *, void *, union _ULARGE_INTEGER *, unsigned int, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1801cc2c0`

## callees

- `0x1800809d0`
- `0x1800c8f68`
- `0x180104920`
- `0x180104e70`
- `0x18010532c`
- `0x18010cb40`
- `0x18014604c`
- `0x1801cc784`
- `0x18023a290`

## import_xrefs

- `KERNEL32!ReadFile` at `0x1801cc8aa`
- `KERNEL32!ReadFile` at `0x1801cc8aa`
- `KERNEL32!CloseHandle` at `0x1801cc85b`
- `KERNEL32!CloseHandle` at `0x1801cc9ec`
- `KERNEL32!CloseHandle` at `0x1801cca70`
- `KERNEL32!CloseHandle` at `0x1801cca8c`
- `KERNEL32!CloseHandle` at `0x1801cc85b`
- `KERNEL32!CloseHandle` at `0x1801cc9ec`
- `KERNEL32!CloseHandle` at `0x1801cca70`
- `KERNEL32!CloseHandle` at `0x1801cca8c`

## pseudocode

```c
int __fastcall CommonUtil::UtilReadFileEx(CommonUtil *this, __int64 *a2, unsigned __int64 *a3, PVOID *a4)
{
  __int64 v9; // r14
  int ManualEvent; // edi
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  int v14; // eax
  int OverlappedResult; // eax
  int v16; // r15d
  int LastError; // eax
  HANDLE v18; // rcx
  const struct _SECURITY_ATTRIBUTES *lpOverlapped; // [rsp+20h] [rbp-50h]
  int v20; // [rsp+28h] [rbp-48h]
  __int64 (__fastcall *v21)(CommonUtil *, struct _OVERLAPPED *, DWORD *, __int64, _DWORD); // [rsp+30h] [rbp-40h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+38h] [rbp-38h] BYREF
  DWORD NumberOfBytesRead; // [rsp+58h] [rbp-18h] BYREF
  HANDLE hObject; // [rsp+60h] [rbp-10h] BYREF

  if ( !this || !a2 || !a3 )
    return -2147024809;
  if ( !a4 )
    return CommonUtil::UtilReadFile(this, a2, a3, 0);
  v9 = *a2;
  if ( (unsigned __int64)*a2 > 0xFFFFFFFF )
  {
    ManualEvent = -2147024362;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_31c6392f1d31353d2174d94cd470b5f6_Traceguids, 2147942934LL);
    return ManualEvent;
  }
  if ( (unsigned int)v9 != v9 )
    return -2147024809;
  *a2 = 0;
  hObject = 0;
  ManualEvent = CommonUtil::UtilCreateManualEvent((CommonUtil *)&hObject, 0, 0, 0, lpOverlapped);
  if ( ManualEvent < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_13;
    v12 = 19;
LABEL_12:
    WPP_SF_d(v11[2], v12, WPP_31c6392f1d31353d2174d94cd470b5f6_Traceguids, (unsigned int)ManualEvent);
LABEL_13:
    if ( hObject )
      CloseHandle(hObject);
    return ManualEvent;
  }
  Overlapped.Internal = 0;
  Overlapped.InternalHigh = 0;
  Overlapped.hEvent = hObject;
  Overlapped.Pointer = *a4;
  NumberOfBytesRead = 0;
  if ( ReadFile(this, a3, v9, &NumberOfBytesRead, &Overlapped) )
  {
    if ( NumberOfBytesRead <= (unsigned int)v9 )
    {
      *a2 = NumberOfBytesRead;
      goto LABEL_56;
    }
    v18 = hObject;
  }
  else
  {
    ManualEvent = HrGetLastError();
    if ( ManualEvent == -2147024858 )
    {
LABEL_17:
      *a2 = 0;
LABEL_56:
      v18 = hObject;
      goto LABEL_57;
    }
    if ( ManualEvent != -2147023899 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_13;
      v12 = 20;
      goto LABEL_12;
    }
    v21 = 0;
    v14 = CommonUtil::CSafeKernel32Proc<int (void *,_OVERLAPPED *,unsigned long *,unsigned long,int)>::Load(v13, &v21);
    if ( v14 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        WPP_31c6392f1d31353d2174d94cd470b5f6_Traceguids,
        (unsigned int)v14);
    if ( v21 )
      OverlappedResult = v21(this, &Overlapped, &NumberOfBytesRead, 0xFFFFFFFFLL, 0);
    else
      OverlappedResult = CommonUtil::UtilGetOverlappedResultEx(
                           this,
                           &Overlapped,
                           (struct _OVERLAPPED *)&NumberOfBytesRead,
                           (unsigned int *)0xFFFFFFFFLL,
                           0,
                           v20);
    v16 = OverlappedResult;
    LastError = HrGetLastError();
    ManualEvent = LastError;
    if ( !v16 )
    {
      switch ( LastError )
      {
        case 268435648:
        case -2147023900:
        case -2147024638:
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
            goto LABEL_13;
          v12 = 22;
          goto LABEL_12;
        case -2147023901:
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              23,
              WPP_31c6392f1d31353d2174d94cd470b5f6_Traceguids,
              2147943395LL);
          if ( hObject )
            CloseHandle(hObject);
          return -2147023901;
        case -2147024858:
          goto LABEL_17;
      }
      if ( LastError < 0 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_13;
        v12 = 24;
        goto LABEL_12;
      }
    }
    v18 = hObject;
    if ( NumberOfBytesRead <= (unsigned int)v9 )
    {
      *a2 = NumberOfBytesRead;
LABEL_57:
      if ( v18 )
        CloseHandle(v18);
      return 0;
    }
  }
  if ( v18 )
    CloseHandle(v18);
  return -2147418113;
}

```

## disassembly

```asm
0x1801cc784  push    rbp
0x1801cc786  push    rbx
0x1801cc787  push    rsi
0x1801cc788  push    rdi
0x1801cc789  push    r12
0x1801cc78b  push    r14
0x1801cc78d  push    r15
0x1801cc78f  mov     rbp, rsp
0x1801cc792  sub     rsp, 70h
0x1801cc796  mov     rax, cs:__security_cookie
0x1801cc79d  xor     rax, rsp
0x1801cc7a0  mov     [rbp+var_8], rax
0x1801cc7a4  mov     r12, r9
0x1801cc7a7  mov     rbx, r8
0x1801cc7aa  mov     rsi, rdx
0x1801cc7ad  mov     r15, rcx
0x1801cc7b0  test    rcx, rcx
0x1801cc7b3  jz      loc_1801CCAD0
0x1801cc7b9  test    rdx, rdx
0x1801cc7bc  jz      loc_1801CCAD0
0x1801cc7c2  test    rbx, rbx
0x1801cc7c5  jz      loc_1801CCAD0
0x1801cc7cb  test    r9, r9
0x1801cc7ce  jnz     short loc_1801CC7DA
0x1801cc7d0  call    ?UtilReadFile@CommonUtil@@YAJPEAXPEA_K0@Z; CommonUtil::UtilReadFile(void *,unsigned __int64 *,void *)
0x1801cc7d5  jmp     loc_1801CCAD5
0x1801cc7da  mov     r14, [rdx]
0x1801cc7dd  mov     eax, 0FFFFFFFFh
0x1801cc7e2  cmp     r14, rax
0x1801cc7e5  ja      loc_1801CCA96
0x1801cc7eb  mov     eax, r14d
0x1801cc7ee  cmp     rax, r14
0x1801cc7f1  jnz     loc_1801CCAD0
0x1801cc7f7  mov     qword ptr [rdx], 0
0x1801cc7fe  mov     [rbp+hObject], 0
0x1801cc806  xor     r9d, r9d; wchar_t *
0x1801cc809  xor     r8d, r8d; int
0x1801cc80c  xor     edx, edx; void **
0x1801cc80e  lea     rcx, [rbp+hObject]; this
0x1801cc812  call    ?UtilCreateManualEvent@CommonUtil@@YAJPEAPEAXHPEB_WPEBU_SECURITY_ATTRIBUTES@@@Z; CommonUtil::UtilCreateManualEvent(void * *,int,wchar_t const *,_SECURITY_ATTRIBUTES const *)
0x1801cc817  mov     edi, eax
0x1801cc819  test    eax, eax
0x1801cc81b  jns     short loc_1801CC866
0x1801cc81d  lea     rbx, WPP_GLOBAL_Control
0x1801cc824  mov     rcx, cs:WPP_GLOBAL_Control
0x1801cc82b  cmp     rcx, rbx
0x1801cc82e  jz      short loc_1801CC84E
0x1801cc830  test    byte ptr [rcx+1Ch], 1
0x1801cc834  jz      short loc_1801CC84E
0x1801cc836  mov     edx, 13h
0x1801cc83b  mov     r9d, edi
0x1801cc83e  lea     r8, WPP_31c6392f1d31353d2174d94cd470b5f6_Traceguids
0x1801cc845  mov     rcx, [rcx+10h]
0x1801cc849  call    WPP_SF_d
0x1801cc84e  mov     rcx, [rbp+hObject]; hObject
0x1801cc852  test    rcx, rcx
0x1801cc855  jz      loc_1801CCACC
0x1801cc85b  call    cs:__imp_CloseHandle
0x1801cc861  jmp     loc_1801CCACC
0x1801cc866  mov     [rbp+Overlapped.Internal], 0
0x1801cc86e  mov     [rbp+Overlapped.InternalHigh], 0
0x1801cc876  mov     rax, [rbp+hObject]
0x1801cc87a  mov     [rbp+Overlapped.hEvent], rax
0x1801cc87e  mov     eax, [r12]
0x1801cc882  mov     dword ptr [rbp+Overlapped.10h], eax
0x1801cc885  mov     eax, [r12+4]
0x1801cc88a  mov     dword ptr [rbp+Overlapped.10h+4], eax
0x1801cc88d  mov     [rbp+NumberOfBytesRead], 0
0x1801cc894  lea     rax, [rbp+Overlapped]
0x1801cc898  mov     [rsp+70h+lpOverlapped], rax; lpOverlapped
0x1801cc89d  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1801cc8a1  mov     r8d, r14d; nNumberOfBytesToRead
0x1801cc8a4  mov     rdx, rbx; lpBuffer
0x1801cc8a7  mov     rcx, r15; hFile
0x1801cc8aa  call    cs:__imp_ReadFile
0x1801cc8b0  test    eax, eax
0x1801cc8b2  jnz     loc_1801CCA61
0x1801cc8b8  call    HrGetLastError
0x1801cc8bd  mov     edi, eax
0x1801cc8bf  mov     r12d, 80070026h
0x1801cc8c5  cmp     eax, r12d
0x1801cc8c8  jnz     short loc_1801CC8D6
0x1801cc8ca  mov     qword ptr [rsi], 0
0x1801cc8d1  jmp     loc_1801CCA83
0x1801cc8d6  cmp     edi, 800703E5h
0x1801cc8dc  jz      short loc_1801CC909
0x1801cc8de  lea     rbx, WPP_GLOBAL_Control
0x1801cc8e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1801cc8ec  cmp     rcx, rbx
0x1801cc8ef  jz      loc_1801CC84E
0x1801cc8f5  test    byte ptr [rcx+1Ch], 1
0x1801cc8f9  jz      loc_1801CC84E
0x1801cc8ff  mov     edx, 14h
0x1801cc904  jmp     loc_1801CC83B
0x1801cc909  mov     [rbp+var_40], 0
0x1801cc911  lea     rdx, [rbp+var_40]
0x1801cc915  call    ?Load@?$CSafeKernel32Proc@$$A6AHPEAXPEAU_OVERLAPPED@@PEAKKH@Z@CommonUtil@@QEAAJPEAP6AHPEAXPEAU_OVERLAPPED@@PEAKKH@Z@Z; CommonUtil::CSafeKernel32Proc<int (void *,_OVERLAPPED *,ulong *,ulong,int)>::Load(int (**)(void *,_OVERLAPPED *,ulong *,ulong,int))
0x1801cc91a  lea     rbx, WPP_GLOBAL_Control
0x1801cc921  test    eax, eax
0x1801cc923  jns     short loc_1801CC94F
0x1801cc925  mov     rcx, cs:WPP_GLOBAL_Control
0x1801cc92c  cmp     rcx, rbx
0x1801cc92f  jz      short loc_1801CC94F
0x1801cc931  test    byte ptr [rcx+1Ch], 2
0x1801cc935  jz      short loc_1801CC94F
0x1801cc937  mov     edx, 15h
0x1801cc93c  mov     r9d, eax
0x1801cc93f  lea     r8, WPP_31c6392f1d31353d2174d94cd470b5f6_Traceguids
0x1801cc946  mov     rcx, [rcx+10h]
0x1801cc94a  call    WPP_SF_d
0x1801cc94f  mov     rax, [rbp+var_40]
0x1801cc953  mov     dword ptr [rsp+70h+lpOverlapped], 0; unsigned int
0x1801cc95b  mov     r9d, 0FFFFFFFFh; unsigned int *
0x1801cc961  lea     r8, [rbp+NumberOfBytesRead]; struct _OVERLAPPED *
0x1801cc965  lea     rdx, [rbp+Overlapped]; void *
0x1801cc969  mov     rcx, r15; this
0x1801cc96c  test    rax, rax
0x1801cc96f  jz      short loc_1801CC979
0x1801cc971  call    cs:__guard_dispatch_icall_fptr
0x1801cc977  jmp     short loc_1801CC97E
0x1801cc979  call    ?UtilGetOverlappedResultEx@CommonUtil@@YAHPEAXPEAU_OVERLAPPED@@PEAKKH@Z; CommonUtil::UtilGetOverlappedResultEx(void *,_OVERLAPPED *,ulong *,ulong,int)
0x1801cc97e  mov     r15d, eax
0x1801cc981  call    HrGetLastError
0x1801cc986  mov     edi, eax
0x1801cc988  test    r15d, r15d
0x1801cc98b  jnz     loc_1801CCA4F
0x1801cc991  cmp     eax, 100000C0h
0x1801cc996  jz      loc_1801CCA2B
0x1801cc99c  cmp     eax, 800703E4h
0x1801cc9a1  jz      loc_1801CCA2B
0x1801cc9a7  cmp     eax, 80070102h
0x1801cc9ac  jz      short loc_1801CCA2B
0x1801cc9ae  mov     r15d, 800703E3h
0x1801cc9b4  cmp     eax, r15d
0x1801cc9b7  jnz     short loc_1801CC9FA
0x1801cc9b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1801cc9c0  cmp     rcx, rbx
0x1801cc9c3  jz      short loc_1801CC9E3
0x1801cc9c5  test    byte ptr [rcx+1Ch], 2
0x1801cc9c9  jz      short loc_1801CC9E3
0x1801cc9cb  mov     edx, 17h
0x1801cc9d0  mov     r9d, r15d
0x1801cc9d3  lea     r8, WPP_31c6392f1d31353d2174d94cd470b5f6_Traceguids
0x1801cc9da  mov     rcx, [rcx+10h]
0x1801cc9de  call    WPP_SF_d
0x1801cc9e3  mov     rcx, [rbp+hObject]; hObject
0x1801cc9e7  test    rcx, rcx
0x1801cc9ea  jz      short loc_1801CC9F2
0x1801cc9ec  call    cs:__imp_CloseHandle
0x1801cc9f2  mov     eax, r15d
0x1801cc9f5  jmp     loc_1801CCAD5
0x1801cc9fa  cmp     edi, r12d
0x1801cc9fd  jz      loc_1801CC8CA
0x1801cca03  test    edi, edi
0x1801cca05  jns     short loc_1801CCA4F
0x1801cca07  mov     rcx, cs:WPP_GLOBAL_Control
0x1801cca0e  cmp     rcx, rbx
0x1801cca11  jz      loc_1801CC84E
0x1801cca17  test    byte ptr [rcx+1Ch], 1
0x1801cca1b  jz      loc_1801CC84E
0x1801cca21  mov     edx, 18h
0x1801cca26  jmp     loc_1801CC83B
0x1801cca2b  mov     rcx, cs:WPP_GLOBAL_Control
0x1801cca32  cmp     rcx, rbx
0x1801cca35  jz      loc_1801CC84E
0x1801cca3b  test    byte ptr [rcx+1Ch], 4
0x1801cca3f  jz      loc_1801CC84E
0x1801cca45  mov     edx, 16h
0x1801cca4a  jmp     loc_1801CC83B
0x1801cca4f  mov     rcx, [rbp+hObject]
0x1801cca53  cmp     [rbp+NumberOfBytesRead], r14d
0x1801cca57  ja      short loc_1801CCA6B
0x1801cca59  mov     eax, [rbp+NumberOfBytesRead]
0x1801cca5c  mov     [rsi], rax
0x1801cca5f  jmp     short loc_1801CCA87
0x1801cca61  cmp     [rbp+NumberOfBytesRead], r14d
0x1801cca65  jbe     short loc_1801CCA7D
0x1801cca67  mov     rcx, [rbp+hObject]; hObject
0x1801cca6b  test    rcx, rcx
0x1801cca6e  jz      short loc_1801CCA76
0x1801cca70  call    cs:__imp_CloseHandle
0x1801cca76  mov     eax, 8000FFFFh
0x1801cca7b  jmp     short loc_1801CCAD5
0x1801cca7d  mov     eax, [rbp+NumberOfBytesRead]
0x1801cca80  mov     [rsi], rax
0x1801cca83  mov     rcx, [rbp+hObject]; hObject
0x1801cca87  test    rcx, rcx
0x1801cca8a  jz      short loc_1801CCA92
0x1801cca8c  call    cs:__imp_CloseHandle
0x1801cca92  xor     eax, eax
0x1801cca94  jmp     short loc_1801CCAD5
0x1801cca96  lea     rbx, WPP_GLOBAL_Control
0x1801cca9d  mov     edi, 80070216h
0x1801ccaa2  mov     rcx, cs:WPP_GLOBAL_Control
0x1801ccaa9  cmp     rcx, rbx
0x1801ccaac  jz      short loc_1801CCACC
0x1801ccaae  test    byte ptr [rcx+1Ch], 1
0x1801ccab2  jz      short loc_1801CCACC
0x1801ccab4  mov     edx, 12h
0x1801ccab9  mov     r9d, edi
0x1801ccabc  lea     r8, WPP_31c6392f1d31353d2174d94cd470b5f6_Traceguids
0x1801ccac3  mov     rcx, [rcx+10h]
0x1801ccac7  call    WPP_SF_d
0x1801ccacc  mov     eax, edi
0x1801ccace  jmp     short loc_1801CCAD5
0x1801ccad0  mov     eax, 80070057h
0x1801ccad5  mov     rcx, [rbp+var_8]
0x1801ccad9  xor     rcx, rsp; StackCookie
0x1801ccadc  call    __security_check_cookie
0x1801ccae1  add     rsp, 70h
0x1801ccae5  pop     r15
0x1801ccae7  pop     r14
0x1801ccae9  pop     r12
0x1801ccaeb  pop     rdi
0x1801ccaec  pop     rsi
0x1801ccaed  pop     rbx
0x1801ccaee  pop     rbp
0x1801ccaef  retn
```
