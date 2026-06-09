# BuildRepairInfos(ulong,tagRepairInfoMap const *,tagPROBLEM_TYPE,_GUID *,ulong,ulong *,tagRepairInfo * *,int)

- ea: `0x18000cf64`
- end: `0x18000d0b2`
- name: `?BuildRepairInfos@@YAJKPEBUtagRepairInfoMap@@W4tagPROBLEM_TYPE@@PEAU_GUID@@KPEAKPEAPEAUtagRepairInfo@@H@Z`
- size: `334`
- prototype: `__int64 __fastcall(unsigned int, const struct tagRepairInfoMap *, enum tagPROBLEM_TYPE, struct _GUID *, unsigned int, unsigned int *, struct tagRepairInfo **, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180007f20`

## callees

- `0x18000cf64`
- `0x18000d2f8`
- `0x18000d864`
- `0x18000dd64`
- `0x18000ded2`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cfd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cfd4`

## pseudocode

```c
__int64 __fastcall BuildRepairInfos(
        unsigned int a1,
        const struct tagRepairInfoMap *a2,
        enum tagPROBLEM_TYPE a3,
        struct _GUID *a4,
        unsigned int a5,
        unsigned int *a6,
        struct tagRepairInfo **a7,
        int a8)
{
  enum tagPROBLEM_TYPE v9; // ebx
  struct tagRepairInfo *v12; // rax
  struct tagRepairInfo *v13; // rsi
  int v14; // ebx
  int v15; // ebp
  unsigned int v16; // edx
  char *v17; // rcx
  __int64 result; // rax

  v9 = a3;
  if ( !a6 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a7 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a2 || !a6 || !a7 || !a4 )
    return 2147942487LL;
  v12 = (struct tagRepairInfo *)CoTaskMemAlloc(0x70u);
  v13 = v12;
  if ( v12 )
  {
    memset_0(v12, 0, sizeof(struct tagRepairInfo));
    v15 = 0;
    if ( a1 )
    {
      while ( 1 )
      {
        v16 = 0;
        while ( 1 )
        {
          v17 = (char *)a2 + 120 * v16;
          if ( (v9 == *(_DWORD *)v17 || a8)
            && *(_QWORD *)&a4[v15].Data1 == *((_QWORD *)v17 + 1)
            && *(_QWORD *)a4[v15].Data4 == *((_QWORD *)v17 + 2) )
          {
            break;
          }
          if ( ++v16 >= a1 )
            goto LABEL_18;
        }
        v14 = PopulateRepairInfo((const struct tagRepairInfoMap *)v17, &v13[v15]);
        if ( v14 < 0 )
          break;
        v9 = a3;
        if ( ++v15 )
        {
          *a6 = 1;
          result = 0;
          *a7 = v13;
          return result;
        }
      }
    }
    else
    {
LABEL_18:
      v14 = -2147023728;
    }
    FreeRepairInfos(v13, 1u, 1);
  }
  else
  {
    v14 = -2147024882;
  }
  *a6 = 0;
  result = (unsigned int)v14;
  *a7 = 0;
  return result;
}

```

## disassembly

```asm
0x18000cf64  mov     [rsp+arg_10], r8d
0x18000cf69  push    rbx
0x18000cf6a  push    rbp
0x18000cf6b  push    rsi
0x18000cf6c  push    rdi
0x18000cf6d  push    r12
0x18000cf6f  push    r13
0x18000cf71  push    r14
0x18000cf73  push    r15
0x18000cf75  sub     rsp, 28h
0x18000cf79  mov     r14, [rsp+68h+arg_28]
0x18000cf81  mov     r13, r9
0x18000cf84  mov     ebx, r8d
0x18000cf87  mov     r15, rdx
0x18000cf8a  mov     r12d, ecx
0x18000cf8d  test    r14, r14
0x18000cf90  jnz     short loc_18000CF97
0x18000cf92  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000cf97  mov     rdi, [rsp+68h+arg_30]
0x18000cf9f  test    rdi, rdi
0x18000cfa2  jnz     short loc_18000CFA9
0x18000cfa4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000cfa9  test    r15, r15
0x18000cfac  jz      loc_18000D09B
0x18000cfb2  test    r14, r14
0x18000cfb5  jz      loc_18000D09B
0x18000cfbb  test    rdi, rdi
0x18000cfbe  jz      loc_18000D09B
0x18000cfc4  test    r13, r13
0x18000cfc7  jz      loc_18000D09B
0x18000cfcd  mov     ebp, 70h ; 'p'
0x18000cfd2  mov     ecx, ebp; cb
0x18000cfd4  call    cs:__imp_CoTaskMemAlloc
0x18000cfdb  nop     dword ptr [rax+rax+00h]
0x18000cfe0  mov     rsi, rax
0x18000cfe3  test    rax, rax
0x18000cfe6  jnz     short loc_18000CFEF
0x18000cfe8  mov     ebx, 8007000Eh
0x18000cfed  jmp     short loc_18000D057
0x18000cfef  mov     r8, rbp; Size
0x18000cff2  xor     edx, edx; Val
0x18000cff4  mov     rcx, rsi; void *
0x18000cff7  call    memset_0
0x18000cffc  xor     ebp, ebp
0x18000cffe  test    r12d, r12d
0x18000d001  jz      short loc_18000D042
0x18000d003  xor     edx, edx
0x18000d005  mov     eax, edx
0x18000d007  imul    rcx, rax, 78h ; 'x'
0x18000d00b  add     rcx, r15; struct tagRepairInfoMap *
0x18000d00e  cmp     ebx, [rcx]
0x18000d010  jz      short loc_18000D01C
0x18000d012  cmp     [rsp+68h+arg_38], 0
0x18000d01a  jz      short loc_18000D03B
0x18000d01c  mov     r8d, ebp
0x18000d01f  add     r8, r8
0x18000d022  mov     r9d, ebp
0x18000d025  mov     rax, [r13+r8*8+0]
0x18000d02a  cmp     rax, [rcx+8]
0x18000d02e  jnz     short loc_18000D03B
0x18000d030  mov     rax, [r13+r8*8+8]
0x18000d035  cmp     rax, [rcx+10h]
0x18000d039  jz      short loc_18000D069
0x18000d03b  inc     edx
0x18000d03d  cmp     edx, r12d
0x18000d040  jb      short loc_18000D005
0x18000d042  mov     ebx, 80070490h
0x18000d047  mov     edx, 1; unsigned int
0x18000d04c  mov     rcx, rsi; pv
0x18000d04f  mov     r8d, edx; int
0x18000d052  call    ?FreeRepairInfos@@YAXPEAUtagRepairInfo@@KH@Z; FreeRepairInfos(tagRepairInfo *,ulong,int)
0x18000d057  mov     dword ptr [r14], 0
0x18000d05e  mov     eax, ebx
0x18000d060  mov     qword ptr [rdi], 0
0x18000d067  jmp     short loc_18000D0A0
0x18000d069  imul    rdx, r9, 70h ; 'p'
0x18000d06d  add     rdx, rsi; struct tagRepairInfo *
0x18000d070  call    ?PopulateRepairInfo@@YAJPEBUtagRepairInfoMap@@PEAUtagRepairInfo@@@Z; PopulateRepairInfo(tagRepairInfoMap const *,tagRepairInfo *)
0x18000d075  mov     ebx, eax
0x18000d077  test    eax, eax
0x18000d079  js      short loc_18000D047
0x18000d07b  mov     ebx, [rsp+68h+arg_10]
0x18000d082  inc     ebp
0x18000d084  cmp     ebp, 1
0x18000d087  jb      loc_18000D003
0x18000d08d  mov     dword ptr [r14], 1
0x18000d094  xor     eax, eax
0x18000d096  mov     [rdi], rsi
0x18000d099  jmp     short loc_18000D0A0
0x18000d09b  mov     eax, 80070057h
0x18000d0a0  add     rsp, 28h
0x18000d0a4  pop     r15
0x18000d0a6  pop     r14
0x18000d0a8  pop     r13
0x18000d0aa  pop     r12
0x18000d0ac  pop     rdi
0x18000d0ad  pop     rsi
0x18000d0ae  pop     rbp
0x18000d0af  pop     rbx
0x18000d0b0  retn
```
