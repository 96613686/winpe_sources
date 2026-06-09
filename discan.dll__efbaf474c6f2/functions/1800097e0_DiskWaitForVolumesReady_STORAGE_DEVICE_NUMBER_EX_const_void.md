# DiskWaitForVolumesReady(_STORAGE_DEVICE_NUMBER_EX const *,void *)

- ea: `0x1800097e0`
- end: `0x18000995a`
- name: `?DiskWaitForVolumesReady@@YAJPEBU_STORAGE_DEVICE_NUMBER_EX@@PEAX@Z`
- size: `378`
- prototype: `__int64 __fastcall(const struct _STORAGE_DEVICE_NUMBER_EX *, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18001ce8c`

## callees

- `0x1800032f8`
- `0x1800064d8`
- `0x180006688`
- `0x1800097e0`

## import_xrefs

- `ntdll!NtWaitForSingleObject` at `0x1800098ed`
- `ntdll!NtWaitForSingleObject` at `0x1800098ed`
- `ntdll!NtDeviceIoControlFile` at `0x1800098d6`
- `ntdll!NtDeviceIoControlFile` at `0x1800098d6`

## string_xrefs

- `0x180009817`: `DiskWaitForVolumesReady`

## pseudocode

```c
__int64 __fastcall DiskWaitForVolumesReady(const struct _STORAGE_DEVICE_NUMBER_EX *a1, void *a2)
{
  __int64 v4; // r9
  NTSTATUS Status; // ebx
  unsigned int v6; // ebx
  const char *v8; // [rsp+60h] [rbp-20h] BYREF
  unsigned int v9; // [rsp+68h] [rbp-18h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-10h] BYREF

  v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  v8 = "DiskWaitForVolumesReady";
  ++*(_WORD *)(v4 + 8);
  *(_QWORD *)(v4 + 16) = "DiskWaitForVolumesReady";
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"DiskWaitForVolumesReady");
  }
  IoStatusBlock = 0;
  Status = NtDeviceIoControlFile(a2, 0, 0, 0, &IoStatusBlock, 0x7421Cu, 0, 0, 0, 0);
  if ( Status == 259 )
  {
    NtWaitForSingleObject(a2, 0, 0);
    Status = IoStatusBlock.Status;
  }
  if ( Status >= 0 )
  {
    v9 = 0;
    v6 = 0;
  }
  else
  {
    v6 = Status | 0x10000000;
    v9 = v6;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        112,
        &WPP_ac7e02637b6a307e043befe010ba928c_Traceguids,
        a1->DeviceNumber,
        v6);
    }
  }
  CHResultImp::~CHResultImp((CHResultImp *)&v8);
  return v6;
}

```

## disassembly

```asm
0x1800097e0  push    rbp
0x1800097e2  push    rbx
0x1800097e3  push    rsi
0x1800097e4  push    rdi
0x1800097e5  push    r15
0x1800097e7  mov     rbp, rsp
0x1800097ea  sub     rsp, 80h
0x1800097f1  mov     r8d, cs:_tls_index
0x1800097f8  mov     rdi, rdx
0x1800097fb  mov     rax, gs:58h
0x180009804  mov     rsi, rcx
0x180009807  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x18000980e  mov     edx, 8
0x180009813  mov     r9, [rax+r8*8]
0x180009817  lea     r8, aDiskwaitforvol; "DiskWaitForVolumesReady"
0x18000981e  mov     eax, 10h
0x180009823  mov     [rbp+var_20], r8
0x180009827  inc     word ptr [rdx+r9]
0x18000982c  movzx   edx, word ptr [rdx+r9]
0x180009831  mov     [rax+r9], r8
0x180009835  cmp     dx, cx
0x180009838  movzx   eax, cx
0x18000983b  cmovb   ax, dx
0x18000983f  cmovb   cx, dx
0x180009843  mov     [rbp+var_30], ax
0x180009847  xor     eax, eax
0x180009849  mov     [rbp+var_2C], eax
0x18000984c  mov     rax, cs:off_180047060; "                                       "...
0x180009853  mov     [rbp+var_28], rax
0x180009857  mov     [rbp+var_2E], cx
0x18000985b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009862  lea     r15, WPP_GLOBAL_Control
0x180009869  cmp     rcx, r15
0x18000986c  jz      short loc_180009891
0x18000986e  test    byte ptr [rcx+1Ch], 1
0x180009872  jz      short loc_180009891
0x180009874  cmp     byte ptr [rcx+19h], 5
0x180009878  jb      short loc_180009891
0x18000987a  mov     rcx, [rcx+10h]; LoggerHandle
0x18000987e  lea     r9, [rbp+var_30]
0x180009882  mov     edx, 0Dh
0x180009887  mov     [rsp+80h+IoStatusBlock], r8; __int64
0x18000988c  call    WPP_SF_aZs
0x180009891  mov     [rsp+80h+OutputBufferLength], 0; OutputBufferLength
0x180009899  lea     rax, [rbp+var_10]
0x18000989d  mov     [rsp+80h+OutputBuffer], 0; OutputBuffer
0x1800098a6  xorps   xmm0, xmm0
0x1800098a9  mov     [rsp+80h+InputBufferLength], 0; InputBufferLength
0x1800098b1  xor     r9d, r9d; ApcContext
0x1800098b4  mov     [rsp+80h+InputBuffer], 0; InputBuffer
0x1800098bd  xor     r8d, r8d; ApcRoutine
0x1800098c0  mov     [rsp+80h+IoControlCode], 7421Ch; IoControlCode
0x1800098c8  xor     edx, edx; Event
0x1800098ca  mov     rcx, rdi; FileHandle
0x1800098cd  mov     [rsp+80h+IoStatusBlock], rax; IoStatusBlock
0x1800098d2  movups  xmmword ptr [rbp+var_10], xmm0
0x1800098d6  call    cs:__imp_NtDeviceIoControlFile
0x1800098dc  mov     ebx, eax
0x1800098de  cmp     eax, 103h
0x1800098e3  jnz     short loc_1800098F6
0x1800098e5  xor     r8d, r8d; Timeout
0x1800098e8  xor     edx, edx; Alertable
0x1800098ea  mov     rcx, rdi; Handle
0x1800098ed  call    cs:__imp_NtWaitForSingleObject
0x1800098f3  mov     ebx, dword ptr [rbp+var_10]
0x1800098f6  test    ebx, ebx
0x1800098f8  jns     short loc_180009938
0x1800098fa  bts     ebx, 1Ch
0x1800098fe  mov     [rbp+var_18], ebx
0x180009901  mov     rcx, cs:WPP_GLOBAL_Control
0x180009908  cmp     rcx, r15
0x18000990b  jz      short loc_180009941
0x18000990d  test    byte ptr [rcx+1Ch], 1
0x180009911  jz      short loc_180009941
0x180009913  cmp     byte ptr [rcx+19h], 2
0x180009917  jb      short loc_180009941
0x180009919  mov     r9d, [rsi+10h]
0x18000991d  lea     r8, WPP_ac7e02637b6a307e043befe010ba928c_Traceguids
0x180009924  mov     rcx, [rcx+10h]
0x180009928  mov     edx, 70h ; 'p'
0x18000992d  mov     dword ptr [rsp+80h+IoStatusBlock], ebx
0x180009931  call    WPP_SF_Dd
0x180009936  jmp     short loc_180009941
0x180009938  mov     [rbp+var_18], 0
0x18000993f  xor     ebx, ebx
0x180009941  lea     rcx, [rbp+var_20]; this
0x180009945  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x18000994a  mov     eax, ebx
0x18000994c  add     rsp, 80h
0x180009953  pop     r15
0x180009955  pop     rdi
0x180009956  pop     rsi
0x180009957  pop     rbx
0x180009958  pop     rbp
0x180009959  retn
```
