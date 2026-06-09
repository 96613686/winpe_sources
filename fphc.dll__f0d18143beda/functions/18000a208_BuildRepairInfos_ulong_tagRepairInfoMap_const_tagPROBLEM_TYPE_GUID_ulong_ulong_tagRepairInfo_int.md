# BuildRepairInfos(ulong,tagRepairInfoMap const *,tagPROBLEM_TYPE,_GUID *,ulong,ulong *,tagRepairInfo * *,int)

- ea: `0x18000a208`
- end: `0x18000a340`
- name: `?BuildRepairInfos@@YAJKPEBUtagRepairInfoMap@@W4tagPROBLEM_TYPE@@PEAU_GUID@@KPEAKPEAPEAUtagRepairInfo@@H@Z`
- size: `312`
- prototype: `__int64 __fastcall(unsigned int, const struct tagRepairInfoMap *, enum tagPROBLEM_TYPE, struct _GUID *, unsigned int, unsigned int *, struct tagRepairInfo **, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180008130`

## callees

- `0x18000a208`
- `0x18000a6cc`
- `0x18000abe8`
- `0x18000edb8`
- `0x180011302`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a278`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a278`

## pseudocode

```c
__int64 __fastcall BuildRepairInfos(
        unsigned int a1,
        const struct tagRepairInfoMap *a2,
        enum tagPROBLEM_TYPE a3,
        struct _GUID *a4,
        unsigned int a5,
        unsigned int *a6,
        struct tagRepairInfo **a7)
{
  enum tagPROBLEM_TYPE v8; // ebx
  struct tagRepairInfo *v11; // rax
  struct tagRepairInfo *v12; // rsi
  int v13; // ebx
  int v14; // ebp
  unsigned int v15; // edx
  char *v16; // rcx
  __int64 result; // rax

  v8 = a3;
  if ( !a6 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a7 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a2 || !a6 || !a7 || !a4 )
    return 2147942487LL;
  v11 = (struct tagRepairInfo *)CoTaskMemAlloc(0x70u);
  v12 = v11;
  if ( v11 )
  {
    memset_0(v11, 0, sizeof(struct tagRepairInfo));
    v14 = 0;
    if ( a1 )
    {
      while ( 1 )
      {
        v15 = 0;
        while ( 1 )
        {
          v16 = (char *)a2 + 120 * v15;
          if ( v8 == *(_DWORD *)v16
            && *(_QWORD *)&a4[v14].Data1 == *((_QWORD *)v16 + 1)
            && *(_QWORD *)a4[v14].Data4 == *((_QWORD *)v16 + 2) )
          {
            break;
          }
          if ( ++v15 >= a1 )
            goto LABEL_17;
        }
        v13 = PopulateRepairInfo((const struct tagRepairInfoMap *)v16, &v12[v14]);
        if ( v13 < 0 )
          break;
        v8 = a3;
        if ( ++v14 )
        {
          *a6 = 1;
          result = 0;
          *a7 = v12;
          return result;
        }
      }
    }
    else
    {
LABEL_17:
      v13 = -2147023728;
    }
    FreeRepairInfos(v12, 1u, 1);
  }
  else
  {
    v13 = -2147024882;
  }
  *a6 = 0;
  result = (unsigned int)v13;
  *a7 = 0;
  return result;
}

```

## disassembly

```asm
0x18000a208  mov     [rsp+arg_10], r8d
0x18000a20d  push    rbx
0x18000a20e  push    rbp
0x18000a20f  push    rsi
0x18000a210  push    rdi
0x18000a211  push    r12
0x18000a213  push    r13
0x18000a215  push    r14
0x18000a217  push    r15
0x18000a219  sub     rsp, 28h
0x18000a21d  mov     r14, [rsp+68h+arg_28]
0x18000a225  mov     r12, r9
0x18000a228  mov     ebx, r8d
0x18000a22b  mov     r15, rdx
0x18000a22e  mov     r13d, ecx
0x18000a231  test    r14, r14
0x18000a234  jnz     short loc_18000A23B
0x18000a236  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a23b  mov     rdi, [rsp+68h+arg_30]
0x18000a243  test    rdi, rdi
0x18000a246  jnz     short loc_18000A24D
0x18000a248  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a24d  test    r15, r15
0x18000a250  jz      loc_18000A32A
0x18000a256  test    r14, r14
0x18000a259  jz      loc_18000A32A
0x18000a25f  test    rdi, rdi
0x18000a262  jz      loc_18000A32A
0x18000a268  test    r12, r12
0x18000a26b  jz      loc_18000A32A
0x18000a271  mov     ebp, 70h ; 'p'
0x18000a276  mov     ecx, ebp; cb
0x18000a278  call    cs:__imp_CoTaskMemAlloc
0x18000a27e  mov     rsi, rax
0x18000a281  test    rax, rax
0x18000a284  jnz     short loc_18000A28D
0x18000a286  mov     ebx, 8007000Eh
0x18000a28b  jmp     short loc_18000A2EA
0x18000a28d  mov     r8, rbp; Size
0x18000a290  xor     edx, edx; Val
0x18000a292  mov     rcx, rsi; void *
0x18000a295  call    memset_0
0x18000a29a  xor     ebp, ebp
0x18000a29c  test    r13d, r13d
0x18000a29f  jz      short loc_18000A2D5
0x18000a2a1  xor     edx, edx
0x18000a2a3  mov     eax, edx
0x18000a2a5  imul    rcx, rax, 78h ; 'x'
0x18000a2a9  add     rcx, r15; struct tagRepairInfoMap *
0x18000a2ac  cmp     ebx, [rcx]
0x18000a2ae  jnz     short loc_18000A2CE
0x18000a2b0  mov     r8d, ebp
0x18000a2b3  add     r8, r8
0x18000a2b6  mov     r9d, ebp
0x18000a2b9  mov     rax, [r12+r8*8]
0x18000a2bd  cmp     rax, [rcx+8]
0x18000a2c1  jnz     short loc_18000A2CE
0x18000a2c3  mov     rax, [r12+r8*8+8]
0x18000a2c8  cmp     rax, [rcx+10h]
0x18000a2cc  jz      short loc_18000A2FC
0x18000a2ce  inc     edx
0x18000a2d0  cmp     edx, r13d
0x18000a2d3  jb      short loc_18000A2A3
0x18000a2d5  mov     ebx, 80070490h
0x18000a2da  mov     edx, 1; unsigned int
0x18000a2df  mov     rcx, rsi; pv
0x18000a2e2  mov     r8d, edx; int
0x18000a2e5  call    ?FreeRepairInfos@@YAXPEAUtagRepairInfo@@KH@Z; FreeRepairInfos(tagRepairInfo *,ulong,int)
0x18000a2ea  mov     dword ptr [r14], 0
0x18000a2f1  mov     eax, ebx
0x18000a2f3  mov     qword ptr [rdi], 0
0x18000a2fa  jmp     short loc_18000A32F
0x18000a2fc  imul    rdx, r9, 70h ; 'p'
0x18000a300  add     rdx, rsi; struct tagRepairInfo *
0x18000a303  call    ?PopulateRepairInfo@@YAJPEBUtagRepairInfoMap@@PEAUtagRepairInfo@@@Z; PopulateRepairInfo(tagRepairInfoMap const *,tagRepairInfo *)
0x18000a308  mov     ebx, eax
0x18000a30a  test    eax, eax
0x18000a30c  js      short loc_18000A2DA
0x18000a30e  mov     ebx, [rsp+68h+arg_10]
0x18000a315  inc     ebp
0x18000a317  cmp     ebp, 1
0x18000a31a  jb      short loc_18000A2A1
0x18000a31c  mov     dword ptr [r14], 1
0x18000a323  xor     eax, eax
0x18000a325  mov     [rdi], rsi
0x18000a328  jmp     short loc_18000A32F
0x18000a32a  mov     eax, 80070057h
0x18000a32f  add     rsp, 28h
0x18000a333  pop     r15
0x18000a335  pop     r14
0x18000a337  pop     r13
0x18000a339  pop     r12
0x18000a33b  pop     rdi
0x18000a33c  pop     rsi
0x18000a33d  pop     rbp
0x18000a33e  pop     rbx
0x18000a33f  retn
```
