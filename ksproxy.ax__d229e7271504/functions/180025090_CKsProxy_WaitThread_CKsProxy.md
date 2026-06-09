# CKsProxy::WaitThread(CKsProxy *)

- ea: `0x180025090`
- end: `0x180025334`
- name: `?WaitThread@CKsProxy@@SAKPEAV1@@Z`
- size: `676`
- prototype: `__int64 __fastcall(unsigned int *Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000bde0`
- `0x180025090`
- `0x18003f33c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002524a`
- `KERNEL32!GetLastError` at `0x18002524a`
- `KERNEL32!SetEvent` at `0x180025308`
- `KERNEL32!SetEvent` at `0x180025308`
- `KERNEL32!CreateEventW` at `0x180025232`
- `KERNEL32!CreateEventW` at `0x180025232`
- `KERNEL32!CloseHandle` at `0x180025174`
- `KERNEL32!CloseHandle` at `0x1800252ee`
- `KERNEL32!CloseHandle` at `0x180025174`
- `KERNEL32!CloseHandle` at `0x1800252ee`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x1800250cd`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x1800250cd`

## pseudocode

```c
__int64 __fastcall CKsProxy::WaitThread(unsigned int *Parameter)
{
  unsigned int v2; // eax
  unsigned int v3; // ecx
  unsigned int v4; // ecx
  unsigned int v5; // edx
  unsigned int i; // edi
  void *v7; // rcx
  __int64 v8; // rax
  HANDLE EventW; // rax
  signed int LastError; // eax
  char *v11; // rcx
  signed int v12; // eax
  __int64 v13; // rdi
  GUID InBuffer; // [rsp+40h] [rbp-40h] BYREF
  int v16; // [rsp+50h] [rbp-30h]
  int v17; // [rsp+54h] [rbp-2Ch]
  HANDLE hObject[2]; // [rsp+58h] [rbp-28h] BYREF
  __int128 v19; // [rsp+68h] [rbp-18h]
  DWORD NumberOfBytesTransferred; // [rsp+A0h] [rbp+20h] BYREF

  while ( 1 )
  {
    while ( WaitForMultipleObjectsEx(Parameter[136], *((const HANDLE **)Parameter + 66), 0, 0xFFFFFFFF, 0) )
    {
      v2 = Parameter[136];
      if ( ++Parameter[144] == v2 - 1 )
        CBaseFilter::NotifyEvent((CBaseFilter *)Parameter, 1, 0, 0);
    }
    v3 = Parameter[140];
    if ( !v3 )
      return 0;
    v4 = v3 - 1;
    if ( v4 )
    {
      if ( v4 == 1 )
      {
        v5 = Parameter[136];
        for ( i = 1; i < v5; ++i )
        {
          if ( *(_QWORD *)(*((_QWORD *)Parameter + 67) + 8LL * i) == *((_QWORD *)Parameter + 71) )
          {
            NumberOfBytesTransferred = 0;
            Parameter[136] = v5 - 1;
            v7 = *(void **)(*((_QWORD *)Parameter + 66) + 8LL * i);
            if ( v7 )
            {
              CloseHandle(v7);
              *(_QWORD *)(*((_QWORD *)Parameter + 66) + 8LL * i) = 0;
            }
            KsSynchronousDeviceControl(
              *(char **)(*((_QWORD *)Parameter + 67) + 8LL * i),
              0x2F000Bu,
              0,
              0,
              0,
              0,
              &NumberOfBytesTransferred);
            v8 = Parameter[136];
            if ( i < (unsigned int)v8 )
            {
              *(_QWORD *)(*((_QWORD *)Parameter + 66) + 8LL * i) = *(_QWORD *)(*((_QWORD *)Parameter + 66) + 8 * v8);
              *(_QWORD *)(*((_QWORD *)Parameter + 67) + 8LL * i) = *(_QWORD *)(*((_QWORD *)Parameter + 67)
                                                                             + 8LL * Parameter[136]);
            }
            break;
          }
        }
      }
    }
    else
    {
      NumberOfBytesTransferred = 0;
      v16 = 4;
      *(_OWORD *)hObject = 0;
      v17 = 1;
      LODWORD(hObject[0]) = 1;
      InBuffer = GUID_7f4bcbe0_9ea5_11cf_a5d6_28db04c10000;
      v19 = 0;
      EventW = CreateEventW(0, 0, 0, 0);
      hObject[1] = EventW;
      if ( EventW )
      {
        *(_QWORD *)(*((_QWORD *)Parameter + 66) + 8LL * Parameter[136]) = EventW;
        v11 = (char *)*((_QWORD *)Parameter + 71);
        v19 = 0;
        v12 = KsSynchronousDeviceControl(v11, 0x2F0007u, &InBuffer, 0x18u, hObject, 0x20u, &NumberOfBytesTransferred);
        v13 = (unsigned int)v12;
        if ( v12 < 0 )
        {
          if ( hObject[1] )
            CloseHandle(hObject[1]);
        }
        else
        {
          *(_QWORD *)(*((_QWORD *)Parameter + 67) + 8LL * Parameter[136]++) = *((_QWORD *)Parameter + 71);
        }
        *((_QWORD *)Parameter + 71) = v13;
      }
      else
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        *((_QWORD *)Parameter + 71) = (unsigned int)LastError;
      }
    }
    SetEvent(*((HANDLE *)Parameter + 69));
  }
}

```

## disassembly

```asm
0x180025090  mov     [rsp-18h+arg_8], rbx
0x180025095  mov     [rsp-18h+arg_10], rsi
0x18002509a  push    rbp
0x18002509b  push    rdi
0x18002509c  push    r15
0x18002509e  mov     rbp, rsp
0x1800250a1  sub     rsp, 80h
0x1800250a8  mov     rbx, rcx
0x1800250ab  mov     r15d, 1
0x1800250b1  mov     rdx, [rbx+210h]; lpHandles
0x1800250b8  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800250bc  mov     ecx, [rbx+220h]; nCount
0x1800250c2  xor     r8d, r8d; bWaitAll
0x1800250c5  mov     [rsp+80h+bAlertable], 0; bAlertable
0x1800250cd  call    cs:__imp_WaitForMultipleObjectsEx
0x1800250d4  nop     dword ptr [rax+rax+00h]
0x1800250d9  test    eax, eax
0x1800250db  jz      short loc_180025108
0x1800250dd  mov     eax, [rbx+220h]
0x1800250e3  add     [rbx+240h], r15d
0x1800250ea  sub     eax, r15d
0x1800250ed  cmp     [rbx+240h], eax
0x1800250f3  jnz     short loc_1800250B1
0x1800250f5  xor     r9d, r9d; __int64
0x1800250f8  xor     r8d, r8d; __int64
0x1800250fb  mov     edx, r15d; int
0x1800250fe  mov     rcx, rbx; this
0x180025101  call    ?NotifyEvent@CBaseFilter@@QEAAJJ_J0@Z; CBaseFilter::NotifyEvent(long,__int64,__int64)
0x180025106  jmp     short loc_1800250B1
0x180025108  mov     ecx, [rbx+230h]
0x18002510e  test    ecx, ecx
0x180025110  jz      loc_180025319
0x180025116  sub     ecx, r15d
0x180025119  jz      loc_1800251FB
0x18002511f  cmp     ecx, r15d
0x180025122  jnz     loc_180025301
0x180025128  mov     edx, [rbx+220h]
0x18002512e  mov     edi, r15d
0x180025131  cmp     edi, edx
0x180025133  jnb     loc_180025301
0x180025139  mov     rcx, [rbx+218h]
0x180025140  mov     rax, [rbx+238h]
0x180025147  mov     esi, edi
0x180025149  cmp     [rcx+rsi*8], rax
0x18002514d  jz      short loc_180025154
0x18002514f  add     edi, r15d
0x180025152  jmp     short loc_180025131
0x180025154  lea     eax, [rdx-1]
0x180025157  mov     [rbp+NumberOfBytesTransferred], 0
0x18002515e  mov     [rbx+220h], eax
0x180025164  mov     rax, [rbx+210h]
0x18002516b  mov     rcx, [rax+rsi*8]; hObject
0x18002516f  test    rcx, rcx
0x180025172  jz      short loc_18002518F
0x180025174  call    cs:__imp_CloseHandle
0x18002517b  nop     dword ptr [rax+rax+00h]
0x180025180  mov     rax, [rbx+210h]
0x180025187  mov     qword ptr [rax+rsi*8], 0
0x18002518f  mov     rcx, [rbx+218h]
0x180025196  lea     rax, [rbp+NumberOfBytesTransferred]
0x18002519a  mov     [rsp+80h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x18002519f  xor     r9d, r9d; nInBufferSize
0x1800251a2  mov     [rsp+80h+var_58], 0; DWORD
0x1800251aa  xor     r8d, r8d; lpInBuffer
0x1800251ad  mov     edx, 2F000Bh; dwIoControlCode
0x1800251b2  mov     qword ptr [rsp+80h+bAlertable], 0; LPVOID
0x1800251bb  mov     rcx, [rcx+rsi*8]; hFile
0x1800251bf  call    KsSynchronousDeviceControl
0x1800251c4  mov     eax, [rbx+220h]
0x1800251ca  cmp     edi, eax
0x1800251cc  jnb     loc_180025301
0x1800251d2  mov     rdx, [rbx+210h]
0x1800251d9  mov     rcx, [rdx+rax*8]
0x1800251dd  mov     [rdx+rsi*8], rcx
0x1800251e1  mov     rdx, [rbx+218h]
0x1800251e8  mov     eax, [rbx+220h]
0x1800251ee  mov     rcx, [rdx+rax*8]
0x1800251f2  mov     [rdx+rsi*8], rcx
0x1800251f6  jmp     loc_180025301
0x1800251fb  movups  xmm1, xmmword ptr cs:_GUID_7f4bcbe0_9ea5_11cf_a5d6_28db04c10000.Data1
0x180025202  mov     [rbp+NumberOfBytesTransferred], 0
0x180025209  xor     r9d, r9d; lpName
0x18002520c  xorps   xmm0, xmm0
0x18002520f  mov     [rbp+var_30], 4
0x180025216  movups  xmmword ptr [rbp+hObject], xmm0
0x18002521a  xor     r8d, r8d; bInitialState
0x18002521d  mov     [rbp+var_2C], r15d
0x180025221  xor     edx, edx; bManualReset
0x180025223  mov     dword ptr [rbp+hObject], r15d
0x180025227  xor     ecx, ecx; lpEventAttributes
0x180025229  movdqu  [rbp+InBuffer], xmm1
0x18002522e  movups  [rbp+var_18], xmm0
0x180025232  call    cs:__imp_CreateEventW
0x180025239  nop     dword ptr [rax+rax+00h]
0x18002523e  mov     [rbp+hObject+8], rax
0x180025242  mov     rdx, rax
0x180025245  test    rax, rax
0x180025248  jnz     short loc_180025270
0x18002524a  call    cs:__imp_GetLastError
0x180025251  nop     dword ptr [rax+rax+00h]
0x180025256  test    eax, eax
0x180025258  jle     short loc_180025262
0x18002525a  movzx   eax, ax
0x18002525d  or      eax, 80070000h
0x180025262  mov     eax, eax
0x180025264  mov     [rbx+238h], rax
0x18002526b  jmp     loc_180025301
0x180025270  mov     ecx, [rbx+220h]
0x180025276  lea     r8, [rbp+InBuffer]; lpInBuffer
0x18002527a  mov     rax, [rbx+210h]
0x180025281  xorps   xmm0, xmm0
0x180025284  mov     r9d, 18h; nInBufferSize
0x18002528a  mov     [rax+rcx*8], rdx
0x18002528e  lea     rax, [rbp+NumberOfBytesTransferred]
0x180025292  mov     rcx, [rbx+238h]; hFile
0x180025299  mov     edx, 2F0007h; dwIoControlCode
0x18002529e  mov     [rsp+80h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x1800252a3  lea     rax, [rbp+hObject]
0x1800252a7  mov     [rsp+80h+var_58], 20h ; ' '; DWORD
0x1800252af  mov     qword ptr [rsp+80h+bAlertable], rax; LPVOID
0x1800252b4  movups  [rbp+var_18], xmm0
0x1800252b8  call    KsSynchronousDeviceControl
0x1800252bd  mov     edi, eax
0x1800252bf  test    eax, eax
0x1800252c1  js      short loc_1800252E5
0x1800252c3  mov     r8d, [rbx+220h]
0x1800252ca  mov     rdx, [rbx+218h]
0x1800252d1  mov     rcx, [rbx+238h]
0x1800252d8  mov     [rdx+r8*8], rcx
0x1800252dc  add     [rbx+220h], r15d
0x1800252e3  jmp     short loc_1800252FA
0x1800252e5  mov     rcx, [rbp+hObject+8]; hObject
0x1800252e9  test    rcx, rcx
0x1800252ec  jz      short loc_1800252FA
0x1800252ee  call    cs:__imp_CloseHandle
0x1800252f5  nop     dword ptr [rax+rax+00h]
0x1800252fa  mov     [rbx+238h], rdi
0x180025301  mov     rcx, [rbx+228h]; hEvent
0x180025308  call    cs:__imp_SetEvent
0x18002530f  nop     dword ptr [rax+rax+00h]
0x180025314  jmp     loc_1800250B1
0x180025319  lea     r11, [rsp+80h+var_s0]
0x180025321  xor     eax, eax
0x180025323  mov     rbx, [r11+28h]
0x180025327  mov     rsi, [r11+30h]
0x18002532b  mov     rsp, r11
0x18002532e  pop     r15
0x180025330  pop     rdi
0x180025331  pop     rbp
0x180025332  retn
```
