# PmQueryWmiDataBlock(_DEVICE_OBJECT *,_IRP *,ulong,ulong,ulong,ulong *,ulong,uchar *)

- ea: `0x1400200e0`
- end: `0x14002023a`
- name: `?PmQueryWmiDataBlock@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@KKKPEAKKPEAE@Z`
- size: `346`
- prototype: `__int64 __usercall@<rax>(PDEVICE_OBJECT DeviceObject@<rcx>, PIRP Irp@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int, unsigned int *, unsigned int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004400`
- `0x140010f20`
- `0x140011140`
- `0x140011440`
- `0x1400200e0`
- `0x1400250f0`

## import_xrefs

- `WMILIB!WmiCompleteRequest` at `0x140020202`
- `WMILIB!WmiCompleteRequest` at `0x140020202`

## pseudocode

```c
NTSTATUS __fastcall PmQueryWmiDataBlock(
        PDEVICE_OBJECT DeviceObject,
        PIRP Irp,
        int a3,
        __int64 a4,
        unsigned int a5,
        unsigned int *a6,
        unsigned int a7,
        struct _DISK_PERFORMANCE *a8)
{
  ULONG v10; // esi
  NTSTATUS v11; // ebx
  struct _PERF_COUNTER_CONTEXT **DeviceExtension; // rdi
  __int64 v13; // rax
  size_t v14; // rbp
  wchar_t pszDest[64]; // [rsp+30h] [rbp-C8h] BYREF

  memset(pszDest, 0, sizeof(pszDest));
  v10 = 0;
  if ( a3
    || (DeviceExtension = (struct _PERF_COUNTER_CONTEXT **)DeviceObject->DeviceExtension,
        *((_DWORD *)DeviceExtension + 42) == -1) )
  {
    v11 = -1073741163;
  }
  else if ( *((_DWORD *)DeviceExtension[90] + 14) )
  {
    RtlStringCchPrintfW(pszDest, 0x40u, L"\\Device\\Harddisk%d\\Partition0", *((unsigned int *)DeviceExtension + 42));
    v13 = -1;
    do
      ++v13;
    while ( pszDest[v13] );
    v14 = (unsigned __int16)(2 * v13);
    v10 = v14 + 90;
    if ( a7 >= (int)v14 + 90 )
    {
      v11 = 0;
      PmWmiCounterQuery(DeviceExtension[90], a8, L"Partmgr ", *((_DWORD *)DeviceExtension + 42));
      LOWORD(a8[1].BytesRead.LowPart) = v14;
      memmove((char *)&a8[1].BytesRead + 2, pszDest, v14);
      *a6 = v10;
    }
    else
    {
      v11 = -1073741789;
    }
  }
  else
  {
    v11 = -1073741823;
  }
  return WmiCompleteRequest(DeviceObject, Irp, v11, v10, 0);
}

```

## disassembly

```asm
0x1400200e0  mov     [rsp+arg_10], rbx
0x1400200e5  push    rbp
0x1400200e6  push    rsi
0x1400200e7  push    rdi
0x1400200e8  push    r12
0x1400200ea  push    r13
0x1400200ec  push    r14
0x1400200ee  push    r15
0x1400200f0  sub     rsp, 0C0h
0x1400200f7  mov     rax, cs:__security_cookie
0x1400200fe  xor     rax, rsp
0x140020101  mov     [rsp+0F8h+var_48], rax
0x140020109  mov     r13, [rsp+0F8h+arg_28]
0x140020111  xor     ebp, ebp
0x140020113  mov     r15, [rsp+0F8h+arg_38]
0x14002011b  mov     ebx, r8d
0x14002011e  mov     r12, rdx
0x140020121  mov     [rsp+0F8h+pszDest], bp
0x140020126  mov     r14, rcx
0x140020129  xor     edx, edx; Val
0x14002012b  lea     r8d, [rbp+7Eh]; Size
0x14002012f  lea     rcx, [rsp+0F8h+var_C6]; void *
0x140020134  call    memset
0x140020139  mov     esi, ebp
0x14002013b  test    ebx, ebx
0x14002013d  jz      short loc_140020149
0x14002013f  mov     ebx, 0C0000295h
0x140020144  jmp     loc_1400201F1
0x140020149  mov     rdi, [r14+40h]
0x14002014d  cmp     dword ptr [rdi+0A8h], 0FFFFFFFFh
0x140020154  jz      short loc_14002013F
0x140020156  mov     rax, [rdi+2D0h]
0x14002015d  mov     ecx, [rax+38h]
0x140020160  test    ecx, ecx
0x140020162  jnz     short loc_14002016E
0x140020164  mov     ebx, 0C0000001h
0x140020169  jmp     loc_1400201F1
0x14002016e  mov     r9d, [rdi+0A8h]
0x140020175  lea     r8, aDeviceHarddisk; "\\Device\\Harddisk%d\\Partition0"
0x14002017c  mov     edx, 40h ; '@'; cchDest
0x140020181  lea     rcx, [rsp+0F8h+pszDest]; pszDest
0x140020186  call    RtlStringCchPrintfW
0x14002018b  lea     rcx, [rsp+0F8h+pszDest]
0x140020190  or      rax, 0FFFFFFFFFFFFFFFFh
0x140020194  inc     rax
0x140020197  cmp     [rcx+rax*2], bp
0x14002019b  jnz     short loc_140020194
0x14002019d  add     ax, ax
0x1400201a0  movzx   ebp, ax
0x1400201a3  lea     esi, [rbp+5Ah]
0x1400201a6  cmp     [rsp+0F8h+arg_30], esi
0x1400201ad  jnb     short loc_1400201B6
0x1400201af  mov     ebx, 0C0000023h
0x1400201b4  jmp     short loc_1400201EF
0x1400201b6  mov     r9d, [rdi+0A8h]; unsigned int
0x1400201bd  lea     r8, aPartmgr_0; "Partmgr "
0x1400201c4  mov     rcx, [rdi+2D0h]; struct _PERF_COUNTER_CONTEXT *
0x1400201cb  mov     rdx, r15; struct _DISK_PERFORMANCE *
0x1400201ce  xor     ebx, ebx
0x1400201d0  call    ?PmWmiCounterQuery@@YAXPEAU_PERF_COUNTER_CONTEXT@@PEAU_DISK_PERFORMANCE@@PEAGK@Z; PmWmiCounterQuery(_PERF_COUNTER_CONTEXT *,_DISK_PERFORMANCE *,ushort *,ulong)
0x1400201d5  mov     r8, rbp; Size
0x1400201d8  mov     [r15+58h], bp
0x1400201dd  lea     rcx, [r15+5Ah]; void *
0x1400201e1  lea     rdx, [rsp+0F8h+pszDest]; Src
0x1400201e6  call    memmove
0x1400201eb  mov     [r13+0], esi
0x1400201ef  xor     ebp, ebp
0x1400201f1  mov     r9d, esi; BufferUsed
0x1400201f4  mov     [rsp+0F8h+PriorityBoost], bpl; PriorityBoost
0x1400201f9  mov     r8d, ebx; Status
0x1400201fc  mov     rdx, r12; Irp
0x1400201ff  mov     rcx, r14; DeviceObject
0x140020202  call    cs:__imp_WmiCompleteRequest
0x140020209  nop     dword ptr [rax+rax+00h]
0x14002020e  mov     rcx, [rsp+0F8h+var_48]
0x140020216  xor     rcx, rsp; StackCookie
0x140020219  call    __security_check_cookie
0x14002021e  mov     rbx, [rsp+0F8h+arg_10]
0x140020226  add     rsp, 0C0h
0x14002022d  pop     r15
0x14002022f  pop     r14
0x140020231  pop     r13
0x140020233  pop     r12
0x140020235  pop     rdi
0x140020236  pop     rsi
0x140020237  pop     rbp
0x140020238  retn
```
