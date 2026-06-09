# PcapTraceVPrintf(char const *,char const *,uint,ulong,char const *,char *)

- ea: `0x180002f7c`
- end: `0x180003100`
- name: `?PcapTraceVPrintf@@YAXPEBD0IK0PEAD@Z`
- size: `388`
- prototype: `void __fastcall(const char *, const char *, unsigned int, unsigned int, const char *, char *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002ee8`

## callees

- `0x180002f7c`
- `0x180003110`
- `0x1800076ac`
- `0x18000bffe`
- `0x18000c030`

## import_xrefs

- `msvcrt!strcpy_s` at `0x180003012`
- `msvcrt!strcpy_s` at `0x180003012`
- `ntdll!EtwEventWriteNoRegistration` at `0x18000309d`
- `ntdll!EtwEventWriteNoRegistration` at `0x18000309d`
- `ntdll!RtlAllocateHeap` at `0x180002fdf`
- `ntdll!RtlAllocateHeap` at `0x180002fdf`
- `ntdll!RtlFreeHeap` at `0x1800030e0`
- `ntdll!RtlFreeHeap` at `0x1800030e0`

## pseudocode

```c
void __fastcall PcapTraceVPrintf(const char *a1, const char *a2, int a3, int a4, char *a5, char *a6)
{
  char *Heap; // rax
  unsigned __int64 v8; // rdx
  char *v9; // rbx
  __int64 v10; // rcx
  __int64 v11; // rax
  int v12; // [rsp+40h] [rbp-49h] BYREF
  int v13; // [rsp+48h] [rbp-41h] BYREF
  int *v14; // [rsp+50h] [rbp-39h] BYREF
  _QWORD v15[6]; // [rsp+58h] [rbp-31h] BYREF
  int v16; // [rsp+88h] [rbp-1h]
  int v17; // [rsp+8Ch] [rbp+3h]
  char *v18; // [rsp+90h] [rbp+7h]
  int v19; // [rsp+98h] [rbp+Fh]
  int v20; // [rsp+9Ch] [rbp+13h]

  v13 = a3;
  v12 = a4;
  v14 = 0;
  memset_0(v15, 0, 0x48u);
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x400u);
  v9 = Heap;
  if ( Heap )
  {
    if ( (int)StringCchVPrintfA(Heap, v8, a5, a6) < 0 )
      strcpy_s(v9, 0x400u, "Parameters too long");
    v15[0] = 4;
    v14 = &v13;
    v15[2] = 4;
    v10 = -1;
    v15[1] = &v12;
    v11 = -1;
    v15[3] = "TRACE";
    v15[4] = 6;
    v15[5] = a2;
    do
      ++v11;
    while ( a2[v11] );
    v17 = 0;
    v16 = v11 + 1;
    do
      ++v10;
    while ( v9[v10] );
    v18 = v9;
    v19 = v10 + 1;
    v20 = 0;
    EtwEventWriteNoRegistration(AE_LOG, AE_PCA_TRACE_EVENT, 5, &v14);
    AslLogPrintf((struct _ASL_LOG *)g_PcapLogTrace, "%s,%04d,%04d,%s,%s\r\n");
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
  }
}

```

## disassembly

```asm
0x180002f7c  push    rbp
0x180002f7e  push    rbx
0x180002f7f  push    rsi
0x180002f80  push    rdi
0x180002f81  push    r14
0x180002f83  lea     rbp, [rsp-27h]
0x180002f88  sub     rsp, 0B0h
0x180002f8f  mov     rax, cs:__security_cookie
0x180002f96  xor     rax, rsp
0x180002f99  mov     [rbp+47h+var_30], rax
0x180002f9d  mov     rsi, [rbp+47h+arg_20]
0x180002fa1  lea     rcx, [rbp+47h+var_78]; void *
0x180002fa5  mov     r14, [rbp+47h+arg_28]
0x180002fa9  mov     rdi, rdx
0x180002fac  xor     edx, edx; Val
0x180002fae  mov     [rbp+47h+var_88], r8d
0x180002fb2  mov     [rbp+47h+var_90], r9d
0x180002fb6  mov     [rbp+47h+var_80], 0
0x180002fbe  lea     r8d, [rdx+48h]; Size
0x180002fc2  call    memset_0
0x180002fc7  mov     rcx, gs:60h
0x180002fd0  mov     edx, 8; Flags
0x180002fd5  mov     r8d, 400h; Size
0x180002fdb  mov     rcx, [rcx+30h]; HeapHandle
0x180002fdf  call    cs:__imp_RtlAllocateHeap
0x180002fe5  mov     rbx, rax
0x180002fe8  test    rax, rax
0x180002feb  jz      loc_1800030E6
0x180002ff1  mov     r9, r14; char *
0x180002ff4  mov     r8, rsi; char *
0x180002ff7  mov     rcx, rax; char *
0x180002ffa  call    ?StringCchVPrintfA@@YAJPEAD_KPEBD0@Z; StringCchVPrintfA(char *,unsigned __int64,char const *,char *)
0x180002fff  test    eax, eax
0x180003001  jns     short loc_180003018
0x180003003  lea     r8, aParametersTooL; "Parameters too long"
0x18000300a  mov     edx, 400h; SizeInBytes
0x18000300f  mov     rcx, rbx; Destination
0x180003012  call    cs:__imp_strcpy_s
0x180003018  lea     rax, [rbp+47h+var_88]
0x18000301c  mov     [rbp+47h+var_78], 4
0x180003024  mov     [rbp+47h+var_80], rax
0x180003028  lea     rsi, aTrace; "TRACE"
0x18000302f  lea     rax, [rbp+47h+var_90]
0x180003033  mov     [rbp+47h+var_68], 4
0x18000303b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000303f  mov     [rbp+47h+var_70], rax
0x180003043  mov     rax, rcx
0x180003046  mov     [rbp+47h+var_60], rsi
0x18000304a  mov     [rbp+47h+var_58], 6
0x180003052  mov     [rbp+47h+var_50], rdi
0x180003056  inc     rax
0x180003059  cmp     byte ptr [rdi+rax], 0
0x18000305d  jnz     short loc_180003056
0x18000305f  inc     eax
0x180003061  mov     [rbp+47h+var_44], 0
0x180003068  mov     [rbp+47h+var_48], eax
0x18000306b  inc     rcx
0x18000306e  cmp     byte ptr [rbx+rcx], 0
0x180003072  jnz     short loc_18000306B
0x180003074  lea     eax, [rcx+1]
0x180003077  mov     [rbp+47h+var_40], rbx
0x18000307b  lea     rcx, AE_LOG
0x180003082  mov     [rbp+47h+var_38], eax
0x180003085  lea     r9, [rbp+47h+var_80]
0x180003089  mov     [rbp+47h+var_34], 0
0x180003090  mov     r8d, 5
0x180003096  lea     rdx, AE_PCA_TRACE_EVENT
0x18000309d  call    cs:__imp_EtwEventWriteNoRegistration
0x1800030a3  mov     eax, [rbp+47h+var_90]
0x1800030a6  lea     rdx, aS04d04dSS; "%s,%04d,%04d,%s,%s\r\n"
0x1800030ad  mov     r9d, [rbp+47h+var_88]
0x1800030b1  mov     r8, rsi
0x1800030b4  mov     rcx, cs:?g_PcapLogTrace@@3_KA; struct _ASL_LOG *
0x1800030bb  mov     [rsp+0D0h+var_A0], rbx
0x1800030c0  mov     [rsp+0D0h+var_A8], rdi
0x1800030c5  mov     [rsp+0D0h+var_B0], eax
0x1800030c9  call    AslLogPrintf
0x1800030ce  mov     rcx, gs:60h
0x1800030d7  mov     r8, rbx; P
0x1800030da  xor     edx, edx; Flags
0x1800030dc  mov     rcx, [rcx+30h]; HeapHandle
0x1800030e0  call    cs:__imp_RtlFreeHeap
0x1800030e6  mov     rcx, [rbp+47h+var_30]
0x1800030ea  xor     rcx, rsp; StackCookie
0x1800030ed  call    __security_check_cookie
0x1800030f2  add     rsp, 0B0h
0x1800030f9  pop     r14
0x1800030fb  pop     rdi
0x1800030fc  pop     rsi
0x1800030fd  pop     rbx
0x1800030fe  pop     rbp
0x1800030ff  retn
```
