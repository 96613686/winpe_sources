# BuildRepairInfos(ulong,tagRepairInfoMap const *,tagPROBLEM_TYPE,_GUID *,ulong,ulong *,tagRepairInfo * *,int)

- ea: `0x180017ac4`
- end: `0x180017bf8`
- name: `?BuildRepairInfos@@YAJKPEBUtagRepairInfoMap@@W4tagPROBLEM_TYPE@@PEAU_GUID@@KPEAKPEAPEAUtagRepairInfo@@H@Z`
- size: `308`
- prototype: `__int64 __fastcall(__int64, const struct tagRepairInfoMap *, __int64, struct _GUID *, unsigned int, unsigned int *, struct tagRepairInfo **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000da10`

## callees

- `0x180017ac4`
- `0x180017d20`
- `0x180018124`
- `0x18001a178`
- `0x18001a5a2`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017b35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017b35`

## pseudocode

```c
__int64 __fastcall BuildRepairInfos(
        __int64 a1,
        const struct tagRepairInfoMap *a2,
        __int64 a3,
        struct _GUID *a4,
        unsigned int a5,
        unsigned int *a6,
        struct tagRepairInfo **a7)
{
  struct tagRepairInfo *v9; // rax
  struct tagRepairInfo *v10; // rbp
  int v11; // ebx
  unsigned int v12; // r15d
  unsigned int i; // edx
  char *v14; // rcx
  __int64 v15; // rax
  __int64 result; // rax
  unsigned int v17; // [rsp+70h] [rbp+8h]

  v17 = a1;
  if ( !a6 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1, a2, a3);
  if ( !a7 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1, a2, a3);
  if ( !a2 || !a6 || !a7 || !a4 )
    return 2147942487LL;
  v9 = (struct tagRepairInfo *)CoTaskMemAlloc(112LL * a5);
  v10 = v9;
  if ( !v9 )
  {
    v11 = -2147024882;
LABEL_24:
    *a6 = 0;
    result = (unsigned int)v11;
    *a7 = 0;
    return result;
  }
  memset_0(v9, 0, 112LL * a5);
  v12 = 0;
  while ( 2 )
  {
    if ( v12 < a5 )
    {
      for ( i = 0; ; ++i )
      {
        if ( i >= v17 )
          goto LABEL_22;
        v14 = (char *)a2 + 120 * i;
        v15 = *(_QWORD *)&a4[v12].Data1 - *((_QWORD *)v14 + 1);
        if ( !v15 )
          v15 = *(_QWORD *)a4[v12].Data4 - *((_QWORD *)v14 + 2);
        if ( !v15 )
          break;
      }
      if ( !v14 )
      {
LABEL_22:
        v11 = -2147023728;
        goto LABEL_23;
      }
      v11 = PopulateRepairInfo((const struct tagRepairInfoMap *)v14, &v10[v12]);
      if ( v11 >= 0 )
      {
        ++v12;
        continue;
      }
LABEL_23:
      FreeRepairInfos(v10, a5, 1);
      goto LABEL_24;
    }
    break;
  }
  *a6 = a5;
  result = 0;
  *a7 = v10;
  return result;
}

```

## disassembly

```asm
0x180017ac4  mov     [rsp+arg_0], ecx
0x180017ac8  push    rbx
0x180017ac9  push    rbp
0x180017aca  push    rsi
0x180017acb  push    rdi
0x180017acc  push    r12
0x180017ace  push    r13
0x180017ad0  push    r14
0x180017ad2  push    r15
0x180017ad4  sub     rsp, 28h
0x180017ad8  mov     rsi, [rsp+68h+arg_28]
0x180017ae0  mov     r12, r9
0x180017ae3  mov     r13, rdx
0x180017ae6  test    rsi, rsi
0x180017ae9  jnz     short loc_180017AF0
0x180017aeb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180017af0  mov     rdi, [rsp+68h+arg_30]
0x180017af8  test    rdi, rdi
0x180017afb  jnz     short loc_180017B02
0x180017afd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180017b02  test    r13, r13
0x180017b05  jz      loc_180017BE2
0x180017b0b  test    rsi, rsi
0x180017b0e  jz      loc_180017BE2
0x180017b14  test    rdi, rdi
0x180017b17  jz      loc_180017BE2
0x180017b1d  test    r12, r12
0x180017b20  jz      loc_180017BE2
0x180017b26  mov     r14d, [rsp+68h+arg_20]
0x180017b2e  imul    rbx, r14, 70h ; 'p'
0x180017b32  mov     rcx, rbx; cb
0x180017b35  call    cs:__imp_CoTaskMemAlloc
0x180017b3b  mov     rbp, rax
0x180017b3e  test    rax, rax
0x180017b41  jnz     short loc_180017B4A
0x180017b43  mov     ebx, 8007000Eh
0x180017b48  jmp     short loc_180017BC7
0x180017b4a  mov     r8, rbx; Size
0x180017b4d  xor     edx, edx; Val
0x180017b4f  mov     rcx, rbp; void *
0x180017b52  call    memset_0
0x180017b57  xor     r15d, r15d
0x180017b5a  cmp     r15d, r14d
0x180017b5d  jnb     short loc_180017BD8
0x180017b5f  xor     edx, edx
0x180017b61  cmp     edx, [rsp+68h+arg_0]
0x180017b65  jnb     short loc_180017BB1
0x180017b67  mov     eax, edx
0x180017b69  imul    rcx, rax, 78h ; 'x'
0x180017b6d  mov     r8d, r15d
0x180017b70  add     r8, r8
0x180017b73  mov     r9d, r15d
0x180017b76  add     rcx, r13; struct tagRepairInfoMap *
0x180017b79  mov     rax, [r12+r8*8]
0x180017b7d  sub     rax, [rcx+8]
0x180017b81  jnz     short loc_180017B8C
0x180017b83  mov     rax, [r12+r8*8+8]
0x180017b88  sub     rax, [rcx+10h]
0x180017b8c  test    rax, rax
0x180017b8f  jz      short loc_180017B95
0x180017b91  inc     edx
0x180017b93  jmp     short loc_180017B61
0x180017b95  test    rcx, rcx
0x180017b98  jz      short loc_180017BB1
0x180017b9a  imul    rdx, r9, 70h ; 'p'
0x180017b9e  add     rdx, rbp; struct tagRepairInfo *
0x180017ba1  call    ?PopulateRepairInfo@@YAJPEBUtagRepairInfoMap@@PEAUtagRepairInfo@@@Z; PopulateRepairInfo(tagRepairInfoMap const *,tagRepairInfo *)
0x180017ba6  mov     ebx, eax
0x180017ba8  test    eax, eax
0x180017baa  js      short loc_180017BB6
0x180017bac  inc     r15d
0x180017baf  jmp     short loc_180017B5A
0x180017bb1  mov     ebx, 80070490h
0x180017bb6  mov     r8d, 1; int
0x180017bbc  mov     edx, r14d; unsigned int
0x180017bbf  mov     rcx, rbp; pv
0x180017bc2  call    ?FreeRepairInfos@@YAXPEAUtagRepairInfo@@KH@Z; FreeRepairInfos(tagRepairInfo *,ulong,int)
0x180017bc7  mov     dword ptr [rsi], 0
0x180017bcd  mov     eax, ebx
0x180017bcf  mov     qword ptr [rdi], 0
0x180017bd6  jmp     short loc_180017BE7
0x180017bd8  mov     [rsi], r14d
0x180017bdb  xor     eax, eax
0x180017bdd  mov     [rdi], rbp
0x180017be0  jmp     short loc_180017BE7
0x180017be2  mov     eax, 80070057h
0x180017be7  add     rsp, 28h
0x180017beb  pop     r15
0x180017bed  pop     r14
0x180017bef  pop     r13
0x180017bf1  pop     r12
0x180017bf3  pop     rdi
0x180017bf4  pop     rsi
0x180017bf5  pop     rbp
0x180017bf6  pop     rbx
0x180017bf7  retn
```
