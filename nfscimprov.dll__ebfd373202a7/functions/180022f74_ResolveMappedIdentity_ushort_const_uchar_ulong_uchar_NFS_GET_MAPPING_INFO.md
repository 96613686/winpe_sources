# ResolveMappedIdentity(ushort const *,uchar,ulong,uchar,_NFS_GET_MAPPING_INFO * *)

- ea: `0x180022f74`
- end: `0x18002318e`
- name: `?ResolveMappedIdentity@@YAKPEBGEKEPEAPEAU_NFS_GET_MAPPING_INFO@@@Z`
- size: `538`
- prototype: `unsigned int __usercall@<eax>(const unsigned __int16 *@<rcx>, unsigned __int8@<dl>, unsigned int@<r8d>, unsigned __int8@<r9b>, struct _NFS_GET_MAPPING_INFO **)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18001139c`
- `0x180011604`

## callees

- `0x180006a54`
- `0x180021084`
- `0x1800210fc`
- `0x1800219fc`
- `0x180022f74`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18002314d`
- `KERNEL32!HeapFree` at `0x18002316e`
- `KERNEL32!HeapFree` at `0x18002314d`
- `KERNEL32!HeapFree` at `0x18002316e`
- `KERNEL32!GetLastError` at `0x18002312a`
- `KERNEL32!GetLastError` at `0x18002312a`
- `KERNEL32!CloseHandle` at `0x180023135`
- `KERNEL32!CloseHandle` at `0x180023135`
- `KERNEL32!HeapAlloc` at `0x180023037`
- `KERNEL32!HeapAlloc` at `0x180023057`
- `KERNEL32!HeapAlloc` at `0x180023037`
- `KERNEL32!HeapAlloc` at `0x180023057`
- `KERNEL32!GetProcessHeap` at `0x180023024`
- `KERNEL32!GetProcessHeap` at `0x180023049`
- `KERNEL32!GetProcessHeap` at `0x18002313f`
- `KERNEL32!GetProcessHeap` at `0x180023160`
- `KERNEL32!GetProcessHeap` at `0x180023024`
- `KERNEL32!GetProcessHeap` at `0x180023049`
- `KERNEL32!GetProcessHeap` at `0x18002313f`
- `KERNEL32!GetProcessHeap` at `0x180023160`
- `KERNEL32!CreateFileW` at `0x180023093`
- `KERNEL32!CreateFileW` at `0x180023093`
- `KERNEL32!DeviceIoControl` at `0x180023120`
- `KERNEL32!DeviceIoControl` at `0x180023120`

## pseudocode

```c
__int64 __fastcall ResolveMappedIdentity(
        const unsigned __int16 *a1,
        char a2,
        int a3,
        char a4,
        struct _NFS_GET_MAPPING_INFO **a5)
{
  DWORD v5; // edi
  unsigned int v8; // r15d
  HANDLE ProcessHeap; // rax
  DWORD ErrorFromHr; // ebx
  LPVOID v12; // rsi
  HANDLE v13; // rax
  void *v14; // rbp
  HANDLE FileW; // r14
  int v16; // eax
  HANDLE v17; // rax
  HANDLE v18; // rax
  DWORD BytesReturned; // [rsp+40h] [rbp-48h] BYREF
  unsigned __int64 v20[8]; // [rsp+48h] [rbp-40h] BYREF
  unsigned int v23; // [rsp+A8h] [rbp+20h] BYREF

  v5 = 2048;
  BytesReturned = 0;
  v23 = 2048;
  v8 = 0;
  if ( !a4 )
  {
    if ( a1 )
    {
      v20[0] = 0;
      if ( (int)StringCchLengthW(a1, 0x7FFFFFFFu, v20) < 0 )
        return 87;
      if ( (int)ULongLongToULong(v20[0] + 1, &v23) < 0 )
        return 87;
      v8 = v23;
      if ( (int)ULongLongToULong(2LL * v23, &v23) < 0 )
        return 87;
      if ( v23 > 0xFFFF )
        return 87;
      v5 = v23 + 12;
      if ( v23 + 12 < v23 )
        return 87;
    }
  }
  ProcessHeap = GetProcessHeap();
  ErrorFromHr = 8;
  v12 = HeapAlloc(ProcessHeap, 8u, v5);
  if ( v12 )
  {
    v13 = GetProcessHeap();
    v14 = HeapAlloc(v13, 8u, v5);
    if ( v14 )
    {
      ErrorFromHr = 0;
      FileW = CreateFileW(L"\\\\.\\NfsSvr", 0x80000000, 0, 0, 3u, 0x1000080u, 0);
      if ( FileW == (HANDLE)-1LL )
        goto LABEL_20;
      *((_DWORD *)v12 + 1) = 2 - (a2 != 0);
      if ( a4 )
      {
        *((_WORD *)v12 + 4) = 0;
        *(_DWORD *)v12 = a3;
      }
      else
      {
        *((_WORD *)v12 + 4) = 2 * v8;
        v16 = StringCchCopyW((unsigned __int16 *)v12 + 5, v8, a1);
        if ( v16 < 0 )
        {
          ErrorFromHr = NfsGetErrorFromHr(v16);
          if ( ErrorFromHr )
          {
LABEL_18:
            CloseHandle(FileW);
            if ( ErrorFromHr )
            {
              v17 = GetProcessHeap();
              HeapFree(v17, 0, v14);
              goto LABEL_21;
            }
LABEL_20:
            *a5 = (struct _NFS_GET_MAPPING_INFO *)v14;
            goto LABEL_21;
          }
        }
      }
      if ( !DeviceIoControl(FileW, 0x10000580u, v12, v5, v14, v5, &BytesReturned, 0) )
        ErrorFromHr = GetLastError();
      goto LABEL_18;
    }
  }
LABEL_21:
  v18 = GetProcessHeap();
  HeapFree(v18, 0, v12);
  return ErrorFromHr;
}

```

## disassembly

```asm
0x180022f74  mov     rax, rsp
0x180022f77  mov     [rax+8], rbx
0x180022f7b  mov     [rax+18h], r8d
0x180022f7f  mov     [rax+10h], dl
0x180022f82  push    rbp
0x180022f83  push    rsi
0x180022f84  push    rdi
0x180022f85  push    r12
0x180022f87  push    r13
0x180022f89  push    r14
0x180022f8b  push    r15
0x180022f8d  sub     rsp, 50h
0x180022f91  xor     r14d, r14d
0x180022f94  mov     edi, 800h
0x180022f99  mov     [rax-48h], r14d
0x180022f9d  mov     r13b, r9b
0x180022fa0  mov     [rax+20h], edi
0x180022fa3  mov     r12, rcx
0x180022fa6  mov     r15d, r14d
0x180022fa9  test    r9b, r9b
0x180022fac  jnz     short loc_180023020
0x180022fae  test    rcx, rcx
0x180022fb1  jz      short loc_180023020
0x180022fb3  lea     r8, [rax-40h]; unsigned __int64 *
0x180022fb7  mov     [rax-40h], r14
0x180022fbb  mov     edx, 7FFFFFFFh; unsigned __int64
0x180022fc0  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180022fc5  test    eax, eax
0x180022fc7  js      short loc_180023016
0x180022fc9  mov     rcx, [rsp+88h+var_40]
0x180022fce  lea     rdx, [rsp+88h+arg_18]; unsigned int *
0x180022fd6  inc     rcx; unsigned __int64
0x180022fd9  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180022fde  test    eax, eax
0x180022fe0  js      short loc_180023016
0x180022fe2  mov     r15d, [rsp+88h+arg_18]
0x180022fea  lea     rdx, [rsp+88h+arg_18]; unsigned int *
0x180022ff2  mov     ecx, r15d
0x180022ff5  add     rcx, rcx; unsigned __int64
0x180022ff8  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180022ffd  test    eax, eax
0x180022fff  js      short loc_180023016
0x180023001  mov     eax, [rsp+88h+arg_18]
0x180023008  cmp     eax, 0FFFFh
0x18002300d  ja      short loc_180023016
0x18002300f  lea     edi, [rax+0Ch]
0x180023012  cmp     edi, eax
0x180023014  jnb     short loc_180023020
0x180023016  mov     eax, 57h ; 'W'
0x18002301b  jmp     loc_180023176
0x180023020  mov     eax, edi
0x180023022  mov     ebp, eax
0x180023024  call    cs:__imp_GetProcessHeap
0x18002302a  mov     ebx, 8
0x18002302f  mov     r8d, ebp; dwBytes
0x180023032  mov     rcx, rax; hHeap
0x180023035  mov     edx, ebx; dwFlags
0x180023037  call    cs:__imp_HeapAlloc
0x18002303d  mov     rsi, rax
0x180023040  test    rax, rax
0x180023043  jz      loc_180023160
0x180023049  call    cs:__imp_GetProcessHeap
0x18002304f  mov     r8d, ebp; dwBytes
0x180023052  mov     edx, ebx; dwFlags
0x180023054  mov     rcx, rax; hHeap
0x180023057  call    cs:__imp_HeapAlloc
0x18002305d  mov     rbp, rax
0x180023060  test    rax, rax
0x180023063  jz      loc_180023160
0x180023069  mov     [rsp+88h+hTemplateFile], r14; hTemplateFile
0x18002306e  lea     rcx, aNfssvr; "\\\\.\\NfsSvr"
0x180023075  mov     [rsp+88h+dwFlagsAndAttributes], 1000080h; dwFlagsAndAttributes
0x18002307d  xor     r9d, r9d; lpSecurityAttributes
0x180023080  xor     r8d, r8d; dwShareMode
0x180023083  mov     [rsp+88h+dwCreationDisposition], 3; dwCreationDisposition
0x18002308b  mov     edx, 80000000h; dwDesiredAccess
0x180023090  mov     ebx, r14d
0x180023093  call    cs:__imp_CreateFileW
0x180023099  mov     r14, rax
0x18002309c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800230a0  jz      loc_180023155
0x1800230a6  neg     [rsp+88h+arg_8]
0x1800230ad  sbb     ecx, ecx
0x1800230af  add     ecx, 2
0x1800230b2  mov     [rsi+4], ecx
0x1800230b5  test    r13b, r13b
0x1800230b8  jz      short loc_1800230CB
0x1800230ba  mov     eax, [rsp+88h+arg_10]
0x1800230c1  xor     ecx, ecx
0x1800230c3  mov     [rsi+8], cx
0x1800230c7  mov     [rsi], eax
0x1800230c9  jmp     short loc_1800230F6
0x1800230cb  movzx   eax, r15w
0x1800230cf  mov     edx, r15d; unsigned __int64
0x1800230d2  add     ax, ax
0x1800230d5  lea     rcx, [rsi+0Ah]; unsigned __int16 *
0x1800230d9  mov     r8, r12; unsigned __int16 *
0x1800230dc  mov     [rsi+8], ax
0x1800230e0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800230e5  test    eax, eax
0x1800230e7  jns     short loc_1800230F6
0x1800230e9  mov     ecx, eax; int
0x1800230eb  call    ?NfsGetErrorFromHr@@YAKJ@Z; NfsGetErrorFromHr(long)
0x1800230f0  mov     ebx, eax
0x1800230f2  test    eax, eax
0x1800230f4  jnz     short loc_180023132
0x1800230f6  mov     [rsp+88h+lpOverlapped], 0; lpOverlapped
0x1800230ff  lea     rax, [rsp+88h+BytesReturned]
0x180023104  mov     [rsp+88h+hTemplateFile], rax; lpBytesReturned
0x180023109  mov     r9d, edi; nInBufferSize
0x18002310c  mov     [rsp+88h+dwFlagsAndAttributes], edi; nOutBufferSize
0x180023110  mov     r8, rsi; lpInBuffer
0x180023113  mov     edx, 10000580h; dwIoControlCode
0x180023118  mov     qword ptr [rsp+88h+dwCreationDisposition], rbp; lpOutBuffer
0x18002311d  mov     rcx, r14; hDevice
0x180023120  call    cs:__imp_DeviceIoControl
0x180023126  test    eax, eax
0x180023128  jnz     short loc_180023132
0x18002312a  call    cs:__imp_GetLastError
0x180023130  mov     ebx, eax
0x180023132  mov     rcx, r14; hObject
0x180023135  call    cs:__imp_CloseHandle
0x18002313b  test    ebx, ebx
0x18002313d  jz      short loc_180023155
0x18002313f  call    cs:__imp_GetProcessHeap
0x180023145  mov     r8, rbp; lpMem
0x180023148  xor     edx, edx; dwFlags
0x18002314a  mov     rcx, rax; hHeap
0x18002314d  call    cs:__imp_HeapFree
0x180023153  jmp     short loc_180023160
0x180023155  mov     rax, [rsp+88h+arg_20]
0x18002315d  mov     [rax], rbp
0x180023160  call    cs:__imp_GetProcessHeap
0x180023166  mov     r8, rsi; lpMem
0x180023169  xor     edx, edx; dwFlags
0x18002316b  mov     rcx, rax; hHeap
0x18002316e  call    cs:__imp_HeapFree
0x180023174  mov     eax, ebx
0x180023176  mov     rbx, [rsp+88h+arg_0]
0x18002317e  add     rsp, 50h
0x180023182  pop     r15
0x180023184  pop     r14
0x180023186  pop     r13
0x180023188  pop     r12
0x18002318a  pop     rdi
0x18002318b  pop     rsi
0x18002318c  pop     rbp
0x18002318d  retn
```
