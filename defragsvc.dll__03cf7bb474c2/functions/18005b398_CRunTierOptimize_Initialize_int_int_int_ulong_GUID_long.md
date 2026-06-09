# CRunTierOptimize::Initialize(int,int,int,ulong,_GUID *,long)

- ea: `0x18005b398`
- end: `0x18005b58b`
- name: `?Initialize@CRunTierOptimize@@AEAAJHHHKPEAU_GUID@@J@Z`
- size: `499`
- prototype: `__int64 __fastcall(CRunTierOptimize *__hidden this, int, int, int, unsigned int, struct _GUID *, LONG lInitialCount)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180036b70`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18005b398`
- `0x180066d54`
- `0x180067b30`

## import_xrefs

- `msvcrt!swprintf_s` at `0x18005b4ad`
- `msvcrt!swprintf_s` at `0x18005b4ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b512`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b512`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005b4f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005b4f9`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x18005b4df`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x18005b4df`

## string_xrefs

- `0x18005b49d`: `Local\DefragMaxParallelThreads-{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRunTierOptimize::Initialize(
        CRunTierOptimize *this,
        int a2,
        __int64 a3,
        int a4,
        unsigned int a5,
        struct _GUID *a6,
        LONG lInitialCount)
{
  __int16 v10; // ax
  HANDLE SemaphoreW; // rbx
  char *v12; // rcx
  signed int LastError; // eax
  unsigned int v14; // ebx
  int Data2; // [rsp+20h] [rbp-E0h]
  int Data3; // [rsp+28h] [rbp-D8h]
  int v18; // [rsp+30h] [rbp-D0h]
  int v19; // [rsp+38h] [rbp-C8h]
  int v20; // [rsp+40h] [rbp-C0h]
  int v21; // [rsp+48h] [rbp-B8h]
  int v22; // [rsp+50h] [rbp-B0h]
  int v23; // [rsp+58h] [rbp-A8h]
  int v24; // [rsp+60h] [rbp-A0h]
  int v25; // [rsp+68h] [rbp-98h]
  int v26; // [rsp+70h] [rbp-90h] BYREF
  __int16 v27; // [rsp+74h] [rbp-8Ch]
  __int16 v28; // [rsp+76h] [rbp-8Ah]
  wchar_t Buffer[264]; // [rsp+B0h] [rbp-50h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v26, "CRunTierOptimize::Initialize", 532, 1);
  *((_DWORD *)this + 190) = a2;
  *((_DWORD *)this + 191) = 1;
  *((_DWORD *)this + 192) = a4;
  *((_DWORD *)this + 193) = a5;
  if ( a6 && lInitialCount > 0 )
  {
    v25 = a6->Data4[7];
    v24 = a6->Data4[6];
    v23 = a6->Data4[5];
    v22 = a6->Data4[4];
    v21 = a6->Data4[3];
    v20 = a6->Data4[2];
    v19 = a6->Data4[1];
    v18 = a6->Data4[0];
    Data3 = a6->Data3;
    Data2 = a6->Data2;
    if ( swprintf_s(
           Buffer,
           0x104u,
           L"Local\\DefragMaxParallelThreads-{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
           a6->Data1,
           Data2,
           Data3,
           v18,
           v19,
           v20,
           v21,
           v22,
           v23,
           v24,
           v25) > 0 )
    {
      SemaphoreW = CreateSemaphoreW(0, lInitialCount, lInitialCount, Buffer);
      v12 = (char *)*((_QWORD *)this + 97);
      if ( (unsigned __int64)(v12 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v12);
      *((_QWORD *)this + 97) = SemaphoreW;
      if ( (((unsigned __int64)SemaphoreW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
      {
        v26 = 0;
        v27 = 572;
        goto LABEL_15;
      }
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v26 = LastError;
      v10 = 572;
    }
    else
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      v26 = -2147418113;
      v10 = 564;
    }
    v28 = v10;
  }
  else if ( (unsigned __int64)(*((_QWORD *)this + 97) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
  }
LABEL_15:
  v14 = v26;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v26);
  return v14;
}

```

## disassembly

```asm
0x18005b398  push    rbp
0x18005b39a  push    rbx
0x18005b39b  push    rsi
0x18005b39c  push    rdi
0x18005b39d  push    r12
0x18005b39f  push    r13
0x18005b3a1  push    r14
0x18005b3a3  push    r15
0x18005b3a5  lea     rbp, [rsp-1D8h]
0x18005b3ad  sub     rsp, 2D8h
0x18005b3b4  mov     rax, cs:__security_cookie
0x18005b3bb  xor     rax, rsp
0x18005b3be  mov     [rbp+210h+var_50], rax
0x18005b3c5  mov     edi, r9d
0x18005b3c8  mov     ebx, edx
0x18005b3ca  mov     r15, rcx
0x18005b3cd  mov     r12, [rbp+210h+arg_28]
0x18005b3d4  mov     r13d, [rbp+210h+lInitialCount]
0x18005b3db  mov     r9d, 1; unsigned __int16
0x18005b3e1  mov     r8d, 214h; unsigned __int16
0x18005b3e7  lea     rdx, aCruntieroptimi_1; "CRunTierOptimize::Initialize"
0x18005b3ee  lea     rcx, [rsp+310h+var_2A0]; this
0x18005b3f3  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18005b3f8  nop
0x18005b3f9  mov     [r15+2F8h], ebx
0x18005b400  mov     dword ptr [r15+2FCh], 1
0x18005b40b  mov     [r15+300h], edi
0x18005b412  mov     eax, [rbp+210h+arg_20]
0x18005b418  mov     [r15+304h], eax
0x18005b41f  test    r12, r12
0x18005b422  jz      loc_18005B543
0x18005b428  test    r13d, r13d
0x18005b42b  jle     loc_18005B543
0x18005b431  movzx   eax, byte ptr [r12+0Fh]
0x18005b437  movzx   ecx, byte ptr [r12+0Eh]
0x18005b43d  movzx   edx, byte ptr [r12+0Dh]
0x18005b443  movzx   r8d, byte ptr [r12+0Ch]
0x18005b449  movzx   r10d, byte ptr [r12+0Bh]
0x18005b44f  movzx   r11d, byte ptr [r12+0Ah]
0x18005b455  movzx   ebx, byte ptr [r12+9]
0x18005b45b  movzx   edi, byte ptr [r12+8]
0x18005b461  movzx   esi, word ptr [r12+6]
0x18005b467  movzx   r14d, word ptr [r12+4]
0x18005b46d  mov     [rsp+310h+var_2A8], eax
0x18005b471  mov     [rsp+310h+var_2B0], ecx
0x18005b475  mov     [rsp+310h+var_2B8], edx
0x18005b479  mov     [rsp+310h+var_2C0], r8d
0x18005b47e  mov     [rsp+310h+var_2C8], r10d
0x18005b483  mov     [rsp+310h+var_2D0], r11d
0x18005b488  mov     [rsp+310h+var_2D8], ebx
0x18005b48c  mov     [rsp+310h+var_2E0], edi
0x18005b490  mov     [rsp+310h+var_2E8], esi
0x18005b494  mov     [rsp+310h+var_2F0], r14d
0x18005b499  mov     r9d, [r12]
0x18005b49d  lea     r8, aLocalDefragmax; "Local\\DefragMaxParallelThreads-{%08x-%"...
0x18005b4a4  mov     edx, 104h; BufferCount
0x18005b4a9  lea     rcx, [rbp+210h+Buffer]; Buffer
0x18005b4ad  call    cs:__imp_swprintf_s
0x18005b4b3  test    eax, eax
0x18005b4b5  jg      short loc_18005B4D3
0x18005b4b7  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005b4bc  mov     [rsp+310h+var_2A0], 8000FFFFh
0x18005b4c4  mov     eax, 234h
0x18005b4c9  mov     [rsp+310h+var_29A], ax
0x18005b4ce  jmp     loc_18005B558
0x18005b4d3  lea     r9, [rbp+210h+Buffer]; lpName
0x18005b4d7  mov     r8d, r13d; lMaximumCount
0x18005b4da  mov     edx, r13d; lInitialCount
0x18005b4dd  xor     ecx, ecx; lpSemaphoreAttributes
0x18005b4df  call    cs:__imp_CreateSemaphoreW
0x18005b4e5  mov     rbx, rax
0x18005b4e8  mov     rcx, [r15+308h]; hObject
0x18005b4ef  lea     rdx, [rcx-1]
0x18005b4f3  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18005b4f7  ja      short loc_18005B4FF
0x18005b4f9  call    cs:__imp_CloseHandle
0x18005b4ff  mov     [r15+308h], rbx
0x18005b506  lea     rax, [rbx+1]
0x18005b50a  test    rax, 0FFFFFFFFFFFFFFFEh
0x18005b510  jnz     short loc_18005B52F
0x18005b512  call    cs:__imp_GetLastError
0x18005b518  test    eax, eax
0x18005b51a  jle     short loc_18005B524
0x18005b51c  movzx   eax, ax
0x18005b51f  or      eax, 80070000h
0x18005b524  mov     [rsp+310h+var_2A0], eax
0x18005b528  mov     eax, 23Ch
0x18005b52d  jmp     short loc_18005B4C9
0x18005b52f  mov     [rsp+310h+var_2A0], 0
0x18005b537  mov     eax, 23Ch
0x18005b53c  mov     [rsp+310h+var_29C], ax
0x18005b541  jmp     short loc_18005B558
0x18005b543  mov     rax, [r15+308h]
0x18005b54a  dec     rax
0x18005b54d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005b551  ja      short loc_18005B558
0x18005b553  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005b558  mov     ebx, [rsp+310h+var_2A0]
0x18005b55c  lea     rcx, [rsp+310h+var_2A0]; this
0x18005b561  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18005b566  mov     eax, ebx
0x18005b568  mov     rcx, [rbp+210h+var_50]
0x18005b56f  xor     rcx, rsp; StackCookie
0x18005b572  call    __security_check_cookie
0x18005b577  add     rsp, 2D8h
0x18005b57e  pop     r15
0x18005b580  pop     r14
0x18005b582  pop     r13
0x18005b584  pop     r12
0x18005b586  pop     rdi
0x18005b587  pop     rsi
0x18005b588  pop     rbx
0x18005b589  pop     rbp
0x18005b58a  retn
```
