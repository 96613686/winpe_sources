# PEH_EngineHelper_Create

- ea: `0x18003e2f0`
- end: `0x18003e455`
- name: `PEH_EngineHelper_Create`
- size: `357`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x18000a300`
- `0x18000a380`
- `0x18003de50`
- `0x18003e2f0`
- `0x18003e460`
- `0x180043cd8`
- `0x180044842`

## import_xrefs

- `msvcrt!malloc` at `0x18003e311`
- `msvcrt!malloc` at `0x18003e311`

## pseudocode

```c
char *__fastcall PEH_EngineHelper_Create(__int64 a1, __int64 a2, __int64 a3)
{
  char *v6; // rax
  char *v7; // rbx
  char v8; // di
  char v9; // bp
  char v10; // r14
  char v11; // si

  v6 = (char *)malloc(0x2D0u);
  v7 = v6;
  if ( !v6 )
    goto LABEL_18;
  memset_0(v6, 0, 0x2D0u);
  *((_QWORD *)v7 + 87) = a2;
  *((_QWORD *)v7 + 88) = a3;
  if ( (unsigned int)GenericCache_New(v7 + 16, L"MSFT_Engine") )
  {
LABEL_17:
    MonitoringHost_Delete(*((void **)v7 + 89));
LABEL_18:
    PEH_EngineHelper_Delete(v7);
    return 0;
  }
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  if ( (unsigned int)GenericCache_New(v7 + 152, L"MSFT_Runspace")
    || (v8 = 1, (unsigned int)GenericCache_New(v7 + 288, L"MSFT_Pipeline"))
    || (v9 = 1, (unsigned int)GenericCache_New(v7 + 424, L"MSFT_PipelineDefinition"))
    || (v10 = 1, (unsigned int)GenericCache_New(v7 + 560, L"MSFT_PipelineExecution")) )
  {
LABEL_9:
    HashMap_Destroy(v7 + 16);
    if ( v8 )
      HashMap_Destroy(v7 + 152);
    if ( v9 )
      HashMap_Destroy(v7 + 288);
    if ( v10 )
      HashMap_Destroy(v7 + 424);
    if ( v11 )
      HashMap_Destroy(v7 + 560);
    goto LABEL_17;
  }
  if ( (unsigned int)MonitoringHost_New(v7 + 712, a1) )
  {
    v11 = 1;
    goto LABEL_9;
  }
  return v7;
}

```

## disassembly

```asm
0x18003e2f0  push    rbx
0x18003e2f2  push    rbp
0x18003e2f3  push    rsi
0x18003e2f4  push    rdi
0x18003e2f5  push    r12
0x18003e2f7  push    r13
0x18003e2f9  push    r14
0x18003e2fb  push    r15
0x18003e2fd  sub     rsp, 28h
0x18003e301  mov     r13, rcx
0x18003e304  mov     ebp, 2D0h
0x18003e309  mov     ecx, ebp; Size
0x18003e30b  mov     rdi, r8
0x18003e30e  mov     rsi, rdx
0x18003e311  call    cs:__imp_malloc
0x18003e317  mov     rbx, rax
0x18003e31a  test    rax, rax
0x18003e31d  jz      loc_18003E435
0x18003e323  mov     r8d, ebp; Size
0x18003e326  xor     edx, edx; Val
0x18003e328  mov     rcx, rax; void *
0x18003e32b  call    memset_0
0x18003e330  lea     rdx, aMsftEngine; "MSFT_Engine"
0x18003e337  mov     [rbx+2B8h], rsi
0x18003e33e  lea     rcx, [rbx+10h]
0x18003e342  mov     [rbx+2C0h], rdi
0x18003e349  call    GenericCache_New
0x18003e34e  test    eax, eax
0x18003e350  jnz     loc_18003E429
0x18003e356  lea     r15, [rbx+98h]
0x18003e35d  xor     dil, dil
0x18003e360  mov     rcx, r15
0x18003e363  lea     rdx, aMsftRunspace; "MSFT_Runspace"
0x18003e36a  xor     bpl, bpl
0x18003e36d  xor     r14b, r14b
0x18003e370  xor     sil, sil
0x18003e373  call    GenericCache_New
0x18003e378  test    eax, eax
0x18003e37a  jnz     short loc_18003E3E0
0x18003e37c  lea     rcx, [rbx+120h]
0x18003e383  mov     dil, 1
0x18003e386  lea     rdx, aMsftPipeline; "MSFT_Pipeline"
0x18003e38d  call    GenericCache_New
0x18003e392  test    eax, eax
0x18003e394  jnz     short loc_18003E3E0
0x18003e396  lea     rcx, [rbx+1A8h]
0x18003e39d  mov     bpl, dil
0x18003e3a0  lea     rdx, aMsftPipelinede; "MSFT_PipelineDefinition"
0x18003e3a7  call    GenericCache_New
0x18003e3ac  test    eax, eax
0x18003e3ae  jnz     short loc_18003E3E0
0x18003e3b0  lea     rcx, [rbx+230h]
0x18003e3b7  mov     r14b, dil
0x18003e3ba  lea     rdx, aMsftPipelineex; "MSFT_PipelineExecution"
0x18003e3c1  call    GenericCache_New
0x18003e3c6  test    eax, eax
0x18003e3c8  jnz     short loc_18003E3E0
0x18003e3ca  lea     rcx, [rbx+2C8h]
0x18003e3d1  mov     rdx, r13
0x18003e3d4  call    MonitoringHost_New
0x18003e3d9  test    eax, eax
0x18003e3db  jz      short loc_18003E450
0x18003e3dd  mov     sil, dil
0x18003e3e0  lea     rcx, [rbx+10h]
0x18003e3e4  call    HashMap_Destroy
0x18003e3e9  test    dil, dil
0x18003e3ec  jz      short loc_18003E3F6
0x18003e3ee  mov     rcx, r15
0x18003e3f1  call    HashMap_Destroy
0x18003e3f6  test    bpl, bpl
0x18003e3f9  jz      short loc_18003E407
0x18003e3fb  lea     rcx, [rbx+120h]
0x18003e402  call    HashMap_Destroy
0x18003e407  test    r14b, r14b
0x18003e40a  jz      short loc_18003E418
0x18003e40c  lea     rcx, [rbx+1A8h]
0x18003e413  call    HashMap_Destroy
0x18003e418  test    sil, sil
0x18003e41b  jz      short loc_18003E429
0x18003e41d  lea     rcx, [rbx+230h]
0x18003e424  call    HashMap_Destroy
0x18003e429  mov     rcx, [rbx+2C8h]; Block
0x18003e430  call    MonitoringHost_Delete
0x18003e435  mov     rcx, rbx
0x18003e438  call    PEH_EngineHelper_Delete
0x18003e43d  xor     eax, eax
0x18003e43f  add     rsp, 28h
0x18003e443  pop     r15
0x18003e445  pop     r14
0x18003e447  pop     r13
0x18003e449  pop     r12
0x18003e44b  pop     rdi
0x18003e44c  pop     rsi
0x18003e44d  pop     rbp
0x18003e44e  pop     rbx
0x18003e44f  retn
0x18003e450  mov     rax, rbx
0x18003e453  jmp     short loc_18003E43F
```
