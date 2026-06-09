# CheckAndEnqueueMonitorDll

- ea: `0x18000d904`
- end: `0x18000dad6`
- name: `CheckAndEnqueueMonitorDll`
- size: `466`
- prototype: `__int64 __fastcall(PCWSTR FileName)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000f698`
- `0x180022dec`

## callees

- `0x180002300`
- `0x180002f48`
- `0x18000d904`
- `0x18001d3d0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000da1e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000da8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000da9c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000daaa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000da1e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000da8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000da9c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000daaa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d9e3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d9e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000d97d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000d97d`
- `SETUPAPI!SetupScanFileQueueW` at `0x18000d9c1`
- `SETUPAPI!SetupScanFileQueueW` at `0x18000d9c1`
- `SETUPAPI!SetupQueueCopyIndirectW` at `0x18000da76`
- `SETUPAPI!SetupQueueCopyIndirectW` at `0x18000da76`

## pseudocode

```c
__int64 __fastcall CheckAndEnqueueMonitorDll(PCWSTR FileName, const WCHAR *a2, void *a3, void *a4)
{
  unsigned int v4; // r14d
  HLOCAL v7; // rsi
  HLOCAL v8; // rdi
  unsigned __int16 *v10; // rbx
  unsigned __int16 *v11; // rax
  DWORD Result; // [rsp+30h] [rbp-D0h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-C8h] BYREF
  HLOCAL v15; // [rsp+40h] [rbp-C0h] BYREF
  __int128 CallbackContext; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v17; // [rsp+58h] [rbp-A8h]
  const WCHAR *v18; // [rsp+60h] [rbp-A0h]
  _SP_FILE_COPY_PARAMS_W CopyParams; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Buffer[264]; // [rsp+D0h] [rbp-30h] BYREF

  v4 = 0;
  v18 = a2;
  Result = 0;
  v7 = 0;
  v17 = 0;
  v8 = 0;
  hMem = 0;
  v15 = 0;
  CallbackContext = 0;
  memset_0(&CopyParams, 0, sizeof(CopyParams));
  if ( GetSystemDirectoryW(Buffer, 0x104u) )
  {
    *(_QWORD *)&CallbackContext = FileName;
    *((_QWORD *)&CallbackContext + 1) = Buffer;
    LODWORD(v17) = 0;
    if ( SetupScanFileQueueW(a3, 4u, 0, MonitorCheckCallback, &CallbackContext, &Result) )
    {
      v10 = 0;
      if ( (_DWORD)v17 )
        goto LABEL_8;
      v11 = (unsigned __int16 *)LocalAlloc(0x40u, 0x208u);
      v10 = v11;
      if ( !v11 )
        return v4;
      if ( !(unsigned int)FindPathOnSource(FileName, a4, v11, (__int64)&hMem, (__int64)&v15) )
      {
        LocalFree(v10);
        v10 = 0;
      }
      v7 = hMem;
      v8 = v15;
      CopyParams.SourceRootPath = v18;
      CopyParams.TargetDirectory = Buffer;
      CopyParams.cbSize = 96;
      CopyParams.QueueHandle = a3;
      CopyParams.SourcePath = v10;
      CopyParams.SourceFilename = FileName;
      CopyParams.SourceDescription = (PCWSTR)hMem;
      CopyParams.SourceTagfile = (PCWSTR)v15;
      CopyParams.TargetFilename = 0;
      CopyParams.CopyStyle = 4;
      CopyParams.LayoutInf = a4;
      CopyParams.SecurityDescriptor = 0;
      if ( SetupQueueCopyIndirectW(&CopyParams) )
LABEL_8:
        v4 = 1;
      if ( v10 )
        LocalFree(v10);
      if ( v7 )
        LocalFree(v7);
      if ( v8 )
        LocalFree(v8);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18000d904  push    rbp
0x18000d906  push    rbx
0x18000d907  push    rsi
0x18000d908  push    rdi
0x18000d909  push    r12
0x18000d90b  push    r13
0x18000d90d  push    r14
0x18000d90f  push    r15
0x18000d911  lea     rbp, [rsp-1F8h]
0x18000d919  sub     rsp, 2F8h
0x18000d920  mov     rax, cs:__security_cookie
0x18000d927  xor     rax, rsp
0x18000d92a  mov     [rbp+230h+var_50], rax
0x18000d931  xor     r14d, r14d
0x18000d934  mov     [rsp+330h+var_2D0], rdx
0x18000d939  mov     r13, r8
0x18000d93c  mov     [rsp+330h+var_300], r14d
0x18000d941  mov     r15, rcx
0x18000d944  xorps   xmm0, xmm0
0x18000d947  xor     eax, eax
0x18000d949  lea     rcx, [rsp+330h+CopyParams]; void *
0x18000d94e  xor     esi, esi
0x18000d950  mov     [rsp+330h+var_2D8], rax
0x18000d955  xor     edi, edi
0x18000d957  mov     [rsp+330h+hMem], rsi
0x18000d95c  lea     r8d, [r14+60h]; Size
0x18000d960  mov     [rsp+330h+var_2F0], rdi
0x18000d965  xor     edx, edx; Val
0x18000d967  mov     r12, r9
0x18000d96a  movups  [rsp+330h+var_2E8], xmm0
0x18000d96f  call    memset_0
0x18000d974  mov     edx, 104h; uSize
0x18000d979  lea     rcx, [rbp+230h+Buffer]; lpBuffer
0x18000d97d  call    cs:__imp_GetSystemDirectoryW
0x18000d983  test    eax, eax
0x18000d985  jz      loc_18000DAB0
0x18000d98b  lea     rax, [rbp+230h+Buffer]
0x18000d98f  mov     qword ptr [rsp+330h+var_2E8], r15
0x18000d994  mov     qword ptr [rsp+330h+var_2E8+8], rax
0x18000d999  lea     r9, ?MonitorCheckCallback@@YAIPEAXI_K1@Z; CallbackRoutine
0x18000d9a0  lea     rax, [rsp+330h+var_300]
0x18000d9a5  mov     dword ptr [rsp+330h+var_2D8], esi
0x18000d9a9  mov     [rsp+330h+Result], rax; Result
0x18000d9ae  lea     edx, [rsi+4]; Flags
0x18000d9b1  lea     rax, [rsp+330h+var_2E8]
0x18000d9b6  xor     r8d, r8d; Window
0x18000d9b9  mov     rcx, r13; FileQueue
0x18000d9bc  mov     [rsp+330h+CallbackContext], rax; CallbackContext
0x18000d9c1  call    cs:__imp_SetupScanFileQueueW
0x18000d9c7  test    eax, eax
0x18000d9c9  jz      loc_18000DAB0
0x18000d9cf  xor     ebx, ebx
0x18000d9d1  cmp     dword ptr [rsp+330h+var_2D8], ebx
0x18000d9d5  jnz     loc_18000DA80
0x18000d9db  mov     edx, 208h; uBytes
0x18000d9e0  lea     ecx, [rsi+40h]; uFlags
0x18000d9e3  call    cs:__imp_LocalAlloc
0x18000d9e9  mov     rbx, rax
0x18000d9ec  test    rax, rax
0x18000d9ef  jz      loc_18000DAB0
0x18000d9f5  lea     rax, [rsp+330h+var_2F0]
0x18000d9fa  mov     r8, rbx; unsigned __int16 *
0x18000d9fd  mov     [rsp+330h+Result], rax; __int64
0x18000da02  mov     rdx, r12; InfHandle
0x18000da05  lea     rax, [rsp+330h+hMem]
0x18000da0a  mov     rcx, r15; FileName
0x18000da0d  mov     [rsp+330h+CallbackContext], rax; __int64
0x18000da12  call    FindPathOnSource
0x18000da17  test    eax, eax
0x18000da19  jnz     short loc_18000DA26
0x18000da1b  mov     rcx, rbx; hMem
0x18000da1e  call    cs:__imp_LocalFree
0x18000da24  xor     ebx, ebx
0x18000da26  mov     rax, [rsp+330h+var_2D0]
0x18000da2b  lea     rcx, [rsp+330h+CopyParams]; CopyParams
0x18000da30  mov     rsi, [rsp+330h+hMem]
0x18000da35  mov     rdi, [rsp+330h+var_2F0]
0x18000da3a  mov     [rbp+230h+CopyParams.SourceRootPath], rax
0x18000da3e  lea     rax, [rbp+230h+Buffer]
0x18000da42  mov     [rbp+230h+CopyParams.TargetDirectory], rax
0x18000da46  mov     [rsp+330h+CopyParams.cbSize], 60h ; '`'
0x18000da4e  mov     [rsp+330h+CopyParams.QueueHandle], r13
0x18000da53  mov     [rbp+230h+CopyParams.SourcePath], rbx
0x18000da57  mov     [rbp+230h+CopyParams.SourceFilename], r15
0x18000da5b  mov     [rbp+230h+CopyParams.SourceDescription], rsi
0x18000da5f  mov     [rbp+230h+CopyParams.SourceTagfile], rdi
0x18000da63  mov     [rbp+230h+CopyParams.TargetFilename], r14
0x18000da67  mov     [rbp+230h+CopyParams.CopyStyle], 4
0x18000da6e  mov     [rbp+230h+CopyParams.LayoutInf], r12
0x18000da72  mov     [rbp+230h+CopyParams.SecurityDescriptor], r14
0x18000da76  call    cs:__imp_SetupQueueCopyIndirectW
0x18000da7c  test    eax, eax
0x18000da7e  jz      short loc_18000DA86
0x18000da80  mov     r14d, 1
0x18000da86  test    rbx, rbx
0x18000da89  jz      short loc_18000DA94
0x18000da8b  mov     rcx, rbx; hMem
0x18000da8e  call    cs:__imp_LocalFree
0x18000da94  test    rsi, rsi
0x18000da97  jz      short loc_18000DAA2
0x18000da99  mov     rcx, rsi; hMem
0x18000da9c  call    cs:__imp_LocalFree
0x18000daa2  test    rdi, rdi
0x18000daa5  jz      short loc_18000DAB0
0x18000daa7  mov     rcx, rdi; hMem
0x18000daaa  call    cs:__imp_LocalFree
0x18000dab0  mov     eax, r14d
0x18000dab3  mov     rcx, [rbp+230h+var_50]
0x18000daba  xor     rcx, rsp; StackCookie
0x18000dabd  call    __security_check_cookie
0x18000dac2  add     rsp, 2F8h
0x18000dac9  pop     r15
0x18000dacb  pop     r14
0x18000dacd  pop     r13
0x18000dacf  pop     r12
0x18000dad1  pop     rdi
0x18000dad2  pop     rsi
0x18000dad3  pop     rbx
0x18000dad4  pop     rbp
0x18000dad5  retn
```
