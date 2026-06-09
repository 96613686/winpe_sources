# CTieredFreeSpaceManager::_Initialize(ushort *,unsigned __int64,ulong)

- ea: `0x18003ac94`
- end: `0x18003adfd`
- name: `?_Initialize@CTieredFreeSpaceManager@@AEAAJPEAG_KK@Z`
- size: `361`
- prototype: `__int64 __fastcall(CTieredFreeSpaceManager *this, unsigned __int16 *, __int64, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180013ae8`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18001a630`
- `0x180026704`
- `0x18003ac94`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003ad1f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003ad1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003ad39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003ad39`

## pseudocode

```c
__int64 __fastcall CTieredFreeSpaceManager::_Initialize(
        CTieredFreeSpaceManager *this,
        unsigned __int16 *a2,
        __int64 a3,
        int a4)
{
  __int16 v8; // ax
  int LastFailureAsHRESULT; // ebx
  HANDLE FileW; // rdi
  __int64 v11; // r8
  __int64 v12; // r9
  char *v13; // rcx
  char *v14; // rdx
  int v16; // [rsp+40h] [rbp-49h] BYREF
  __int16 v17; // [rsp+44h] [rbp-45h]
  __int16 v18; // [rsp+46h] [rbp-43h]
  int v19; // [rsp+78h] [rbp-11h] BYREF
  __int16 v20; // [rsp+7Ch] [rbp-Dh]
  __int16 v21; // [rsp+7Eh] [rbp-Bh]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v16, "CTieredFreeSpaceManager::_Initialize", 870, 1);
  v8 = 872;
  if ( a2 )
  {
    v16 = 0;
    v17 = 872;
    FileW = CreateFileW(a2, 0xC0000000, 3u, 0, 3u, 0x20000080u, 0);
    v13 = (char *)*((_QWORD *)this + 9);
    v14 = v13 - 1;
    if ( (unsigned __int64)(v13 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v13);
    *((_QWORD *)this + 9) = FileW;
    if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      v16 = 0;
      v17 = 883;
      *((_QWORD *)this + 10) = a3;
      *((_DWORD *)this + 22) = a4;
      CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v19, "CTieredFreeSpaceManager::_DiscoverTiers", 839, 1);
      v19 = DiscoverTiers((char *)this + 72, (char *)this + 96);
      if ( v19 >= 0 )
        v20 = 841;
      else
        v21 = 841;
      CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v19);
      LastFailureAsHRESULT = (*(__int64 (__fastcall **)(CTieredFreeSpaceManager *))(*(_QWORD *)this + 24LL))(this);
      v16 = LastFailureAsHRESULT;
      v8 = 896;
      if ( LastFailureAsHRESULT >= 0 )
      {
        v17 = 896;
        goto LABEL_13;
      }
    }
    else
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v13, v14, v11, v12);
      v16 = LastFailureAsHRESULT;
      v8 = 883;
    }
  }
  else
  {
    LastFailureAsHRESULT = -2147024809;
    v16 = -2147024809;
  }
  v18 = v8;
LABEL_13:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v16);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18003ac94  push    rbp
0x18003ac96  push    rbx
0x18003ac97  push    rsi
0x18003ac98  push    rdi
0x18003ac99  push    r14
0x18003ac9b  push    r15
0x18003ac9d  lea     rbp, [rsp-2Fh]
0x18003aca2  sub     rsp, 0B8h
0x18003aca9  mov     r14d, r9d
0x18003acac  mov     r15, r8
0x18003acaf  mov     rdi, rdx
0x18003acb2  mov     rbx, rcx
0x18003acb5  mov     r9d, 1; unsigned __int16
0x18003acbb  mov     r8d, 366h; unsigned __int16
0x18003acc1  lea     rdx, aCtieredfreespa_11; "CTieredFreeSpaceManager::_Initialize"
0x18003acc8  lea     rcx, [rbp+57h+var_A0]; this
0x18003accc  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18003acd1  nop
0x18003acd2  mov     eax, 368h
0x18003acd7  test    rdi, rdi
0x18003acda  jnz     short loc_18003ACED
0x18003acdc  mov     ebx, 80070057h
0x18003ace1  mov     [rbp+57h+var_A0], ebx
0x18003ace4  mov     [rbp+57h+var_9A], ax
0x18003ace8  jmp     loc_18003ADE2
0x18003aced  mov     [rbp+57h+var_A0], 0
0x18003acf4  mov     [rbp+57h+var_9C], ax
0x18003acf8  mov     [rsp+0E0h+hTemplateFile], 0; hTemplateFile
0x18003ad01  mov     [rsp+0E0h+dwFlagsAndAttributes], 20000080h; dwFlagsAndAttributes
0x18003ad09  mov     r8d, 3; dwShareMode
0x18003ad0f  mov     [rsp+0E0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18003ad14  xor     r9d, r9d; lpSecurityAttributes
0x18003ad17  mov     edx, 0C0000000h; dwDesiredAccess
0x18003ad1c  mov     rcx, rdi; lpFileName
0x18003ad1f  call    cs:__imp_CreateFileW
0x18003ad25  mov     rdi, rax
0x18003ad28  lea     rsi, [rbx+48h]
0x18003ad2c  mov     rcx, [rsi]; hObject
0x18003ad2f  lea     rdx, [rcx-1]
0x18003ad33  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18003ad37  ja      short loc_18003AD3F
0x18003ad39  call    cs:__imp_CloseHandle
0x18003ad3f  mov     [rsi], rdi
0x18003ad42  lea     rax, [rdi+1]
0x18003ad46  test    rax, 0FFFFFFFFFFFFFFFEh
0x18003ad4c  jnz     short loc_18003AD5F
0x18003ad4e  call    GetLastFailureAsHRESULT
0x18003ad53  mov     ebx, eax
0x18003ad55  mov     [rbp+57h+var_A0], eax
0x18003ad58  mov     eax, 373h
0x18003ad5d  jmp     short loc_18003ACE4
0x18003ad5f  mov     [rbp+57h+var_A0], 0
0x18003ad66  mov     eax, 373h
0x18003ad6b  mov     [rbp+57h+var_9C], ax
0x18003ad6f  mov     [rbx+50h], r15
0x18003ad73  mov     [rbx+58h], r14d
0x18003ad77  mov     r9d, 1; unsigned __int16
0x18003ad7d  lea     r8d, [rax-2Ch]; unsigned __int16
0x18003ad81  lea     rdx, aCtieredfreespa_7; "CTieredFreeSpaceManager::_DiscoverTiers"
0x18003ad88  lea     rcx, [rbp+57h+var_68]; this
0x18003ad8c  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18003ad91  nop
0x18003ad92  lea     rdx, [rbx+60h]
0x18003ad96  mov     rcx, rsi
0x18003ad99  call    ?DiscoverTiers@@YAJAEAV?$CSxBaseHandle@PEAX$0?0$0A@$1?CloseHandle@@YAHPEAX@Z@@AEAVCTieredVolumeInfo@@@Z; DiscoverTiers(CSxBaseHandle<void *,-1,0,&CloseHandle(void *)> &,CTieredVolumeInfo &)
0x18003ad9e  mov     [rbp+57h+var_68], eax
0x18003ada1  test    eax, eax
0x18003ada3  mov     eax, 349h
0x18003ada8  jns     short loc_18003ADB0
0x18003adaa  mov     [rbp+57h+var_62], ax
0x18003adae  jmp     short loc_18003ADB4
0x18003adb0  mov     [rbp+57h+var_64], ax
0x18003adb4  lea     rcx, [rbp+57h+var_68]; this
0x18003adb8  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18003adbd  mov     rax, [rbx]
0x18003adc0  mov     rcx, rbx
0x18003adc3  mov     rax, [rax+18h]
0x18003adc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003adcc  mov     ebx, eax
0x18003adce  mov     [rbp+57h+var_A0], eax
0x18003add1  test    eax, eax
0x18003add3  mov     eax, 380h
0x18003add8  js      loc_18003ACE4
0x18003adde  mov     [rbp+57h+var_9C], ax
0x18003ade2  lea     rcx, [rbp+57h+var_A0]; this
0x18003ade6  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18003adeb  mov     eax, ebx
0x18003aded  add     rsp, 0B8h
0x18003adf4  pop     r15
0x18003adf6  pop     r14
0x18003adf8  pop     rdi
0x18003adf9  pop     rsi
0x18003adfa  pop     rbx
0x18003adfb  pop     rbp
0x18003adfc  retn
```
