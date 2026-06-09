# StorageQueryProperty(void *,_STORAGE_PROPERTY_QUERY const *,ulong,ATL::CHeapPtr<_STORAGE_DESCRIPTOR_HEADER,ATL::CCRTAllocator> &,ulong &,ulong *)

- ea: `0x1800105d8`
- end: `0x180010817`
- name: `?StorageQueryProperty@@YAJPEAXPEBU_STORAGE_PROPERTY_QUERY@@KAEAV?$CHeapPtr@U_STORAGE_DESCRIPTOR_HEADER@@VCCRTAllocator@ATL@@@ATL@@AEAKPEAK@Z`
- size: `575`
- prototype: `__int64 __usercall@<rax>(HANDLE Handle@<rcx>, PVOID InputBuffer@<rdx>, __int64, __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000d2ec`
- `0x18000d4f0`
- `0x18000d730`
- `0x18000e2f8`

## callees

- `0x1800032f8`
- `0x180006498`
- `0x180006688`
- `0x1800105d8`

## import_xrefs

- `msvcrt!realloc` at `0x180010729`
- `msvcrt!realloc` at `0x180010729`
- `ntdll!NtWaitForSingleObject` at `0x1800106fa`
- `ntdll!NtWaitForSingleObject` at `0x1800106fa`
- `ntdll!NtDeviceIoControlFile` at `0x1800106e3`
- `ntdll!NtDeviceIoControlFile` at `0x1800106e3`

## pseudocode

```c
__int64 __fastcall StorageQueryProperty(HANDLE Handle, PVOID InputBuffer, __int64 a3, void **a4, ULONG *a5, _DWORD *a6)
{
  _QWORD *ThreadLocalStoragePointer; // rax
  USHORT Length; // cx
  __int64 v11; // rdx
  USHORT v12; // dx
  USHORT v13; // ax
  NTSTATUS Status; // ebx
  ULONG_PTR Information; // r9
  unsigned int *v16; // rax
  size_t v17; // rdx
  ULONG *v18; // rax
  unsigned int v19; // ebx
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  PVOID OutputBuffer; // [rsp+40h] [rbp-30h]
  ULONG OutputBufferLength; // [rsp+48h] [rbp-28h]
  const char *v25; // [rsp+50h] [rbp-20h] BYREF
  unsigned int v26; // [rsp+58h] [rbp-18h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-10h] BYREF

  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  Length = GlobalIndentString.Length;
  v26 = 0;
  v11 = ThreadLocalStoragePointer[tls_index];
  v25 = "StorageQueryProperty";
  *(_QWORD *)(v11 + 16) = "StorageQueryProperty";
  v12 = ++*(_WORD *)(v11 + 8);
  v13 = Length;
  if ( v12 < Length )
  {
    v13 = v12;
    Length = v12;
  }
  LOWORD(IoStatusBlock.Status) = v13;
  HIDWORD(IoStatusBlock.Pointer) = 0;
  IoStatusBlock.Information = (ULONG_PTR)off_180047060;
  WORD1(IoStatusBlock.Pointer) = Length;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"StorageQueryProperty");
  }
  if ( a6 )
    *a6 = 0;
  while ( 1 )
  {
    OutputBufferLength = *a5;
    OutputBuffer = *a4;
    IoStatusBlock = 0;
    Status = NtDeviceIoControlFile(
               Handle,
               0,
               0,
               0,
               &IoStatusBlock,
               0x2D1400u,
               InputBuffer,
               0xCu,
               OutputBuffer,
               OutputBufferLength);
    if ( Status == 259 )
    {
      NtWaitForSingleObject(Handle, 0, 0);
      Status = IoStatusBlock.Status;
    }
    if ( Status < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          77,
          &WPP_ac7e02637b6a307e043befe010ba928c_Traceguids,
          (unsigned int)Status);
      }
      v19 = Status | 0x10000000;
      goto LABEL_36;
    }
    Information = IoStatusBlock.Information;
    if ( IoStatusBlock.Information < 8 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_30;
      }
      v21 = 78;
      goto LABEL_29;
    }
    v16 = (unsigned int *)*a4;
    if ( *((_DWORD *)*a4 + 1) < 8u )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_30;
      }
      Information = v16[1];
      v21 = 79;
LABEL_29:
      WPP_SF_d(v20[2], v21, &WPP_ac7e02637b6a307e043befe010ba928c_Traceguids, Information);
LABEL_30:
      v19 = -2147467259;
      goto LABEL_36;
    }
    v17 = v16[1];
    if ( v17 <= IoStatusBlock.Information )
      break;
    v18 = (ULONG *)realloc(*a4, v17);
    if ( !v18 )
    {
      v19 = -2147024882;
LABEL_36:
      v26 = v19;
      goto LABEL_37;
    }
    *a4 = v18;
    *a5 = v18[1];
  }
  if ( a6 )
    *a6 = IoStatusBlock.Information;
  v19 = 0;
LABEL_37:
  CHResultImp::~CHResultImp((CHResultImp *)&v25);
  return v19;
}

```

## disassembly

```asm
0x1800105d8  push    rbp
0x1800105da  push    rbx
0x1800105db  push    rsi
0x1800105dc  push    rdi
0x1800105dd  push    r12
0x1800105df  push    r14
0x1800105e1  push    r15
0x1800105e3  mov     rbp, rsp
0x1800105e6  sub     rsp, 70h
0x1800105ea  mov     r8d, cs:_tls_index
0x1800105f1  mov     r12, rdx
0x1800105f4  mov     rax, gs:58h
0x1800105fd  mov     r15, rcx
0x180010600  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x180010607  mov     r14, r9
0x18001060a  mov     [rbp+var_18], 0
0x180010611  mov     rdx, [rax+r8*8]
0x180010615  lea     r8, aStoragequerypr; "StorageQueryProperty"
0x18001061c  mov     eax, 10h
0x180010621  mov     [rbp+var_20], r8
0x180010625  mov     [rax+rdx], r8
0x180010629  mov     eax, 8
0x18001062e  inc     word ptr [rax+rdx]
0x180010632  movzx   edx, word ptr [rax+rdx]
0x180010636  movzx   eax, cx
0x180010639  cmp     dx, cx
0x18001063c  cmovb   ax, dx
0x180010640  cmovb   cx, dx
0x180010644  mov     word ptr [rbp+var_10], ax
0x180010648  xor     eax, eax
0x18001064a  mov     dword ptr [rbp+var_10+4], eax
0x18001064d  mov     rax, cs:off_180047060; "                                       "...
0x180010654  mov     [rbp+var_10.Information], rax
0x180010658  mov     word ptr [rbp+var_10+2], cx
0x18001065c  mov     rcx, cs:WPP_GLOBAL_Control
0x180010663  lea     rax, WPP_GLOBAL_Control
0x18001066a  cmp     rcx, rax
0x18001066d  jz      short loc_180010692
0x18001066f  test    byte ptr [rcx+1Ch], 1
0x180010673  jz      short loc_180010692
0x180010675  cmp     byte ptr [rcx+19h], 5
0x180010679  jb      short loc_180010692
0x18001067b  mov     rcx, [rcx+10h]; LoggerHandle
0x18001067f  lea     r9, [rbp+var_10]
0x180010683  mov     edx, 0Dh
0x180010688  mov     [rsp+70h+IoStatusBlock], r8; __int64
0x18001068d  call    WPP_SF_aZs
0x180010692  mov     rdi, [rbp+arg_28]
0x180010696  test    rdi, rdi
0x180010699  jz      short loc_1800106A1
0x18001069b  mov     dword ptr [rdi], 0
0x1800106a1  mov     rsi, [rbp+arg_20]
0x1800106a5  mov     eax, [rsi]
0x1800106a7  xorps   xmm0, xmm0
0x1800106aa  mov     [rsp+70h+OutputBufferLength], eax; OutputBufferLength
0x1800106ae  xor     r9d, r9d; ApcContext
0x1800106b1  mov     rax, [r14]
0x1800106b4  xor     r8d, r8d; ApcRoutine
0x1800106b7  mov     [rsp+70h+OutputBuffer], rax; OutputBuffer
0x1800106bc  xor     edx, edx; Event
0x1800106be  mov     [rsp+70h+InputBufferLength], 0Ch; InputBufferLength
0x1800106c6  lea     rax, [rbp+var_10]
0x1800106ca  mov     [rsp+70h+InputBuffer], r12; InputBuffer
0x1800106cf  mov     rcx, r15; FileHandle
0x1800106d2  mov     [rsp+70h+IoControlCode], 2D1400h; IoControlCode
0x1800106da  mov     [rsp+70h+IoStatusBlock], rax; IoStatusBlock
0x1800106df  movups  xmmword ptr [rbp+var_10], xmm0
0x1800106e3  call    cs:__imp_NtDeviceIoControlFile
0x1800106e9  mov     ebx, eax
0x1800106eb  cmp     eax, 103h
0x1800106f0  jnz     short loc_180010703
0x1800106f2  xor     r8d, r8d; Timeout
0x1800106f5  xor     edx, edx; Alertable
0x1800106f7  mov     rcx, r15; Handle
0x1800106fa  call    cs:__imp_NtWaitForSingleObject
0x180010700  mov     ebx, dword ptr [rbp+var_10]
0x180010703  test    ebx, ebx
0x180010705  js      loc_1800107BF
0x18001070b  mov     r9, [rbp+var_10.Information]
0x18001070f  cmp     r9, 8
0x180010713  jb      short loc_180010784
0x180010715  mov     rax, [r14]
0x180010718  cmp     dword ptr [rax+4], 8
0x18001071c  jb      short loc_18001075A
0x18001071e  mov     edx, [rax+4]; Size
0x180010721  cmp     rdx, r9
0x180010724  jbe     short loc_18001074B
0x180010726  mov     rcx, rax; Block
0x180010729  call    cs:__imp_realloc
0x18001072f  test    rax, rax
0x180010732  jz      short loc_180010741
0x180010734  mov     [r14], rax
0x180010737  mov     eax, [rax+4]
0x18001073a  mov     [rsi], eax
0x18001073c  jmp     loc_1800106A5
0x180010741  mov     ebx, 8007000Eh
0x180010746  jmp     loc_1800107FA
0x18001074b  test    rdi, rdi
0x18001074e  jz      short loc_180010753
0x180010750  mov     [rdi], r9d
0x180010753  xor     ebx, ebx
0x180010755  jmp     loc_1800107FD
0x18001075a  mov     rcx, cs:WPP_GLOBAL_Control
0x180010761  lea     rdx, WPP_GLOBAL_Control
0x180010768  cmp     rcx, rdx
0x18001076b  jz      short loc_1800107B8
0x18001076d  test    byte ptr [rcx+1Ch], 1
0x180010771  jz      short loc_1800107B8
0x180010773  cmp     byte ptr [rcx+19h], 2
0x180010777  jb      short loc_1800107B8
0x180010779  mov     r9d, [rax+4]
0x18001077d  mov     edx, 4Fh ; 'O'
0x180010782  jmp     short loc_1800107A8
0x180010784  mov     rcx, cs:WPP_GLOBAL_Control
0x18001078b  lea     rdx, WPP_GLOBAL_Control
0x180010792  cmp     rcx, rdx
0x180010795  jz      short loc_1800107B8
0x180010797  test    byte ptr [rcx+1Ch], 1
0x18001079b  jz      short loc_1800107B8
0x18001079d  cmp     byte ptr [rcx+19h], 2
0x1800107a1  jb      short loc_1800107B8
0x1800107a3  mov     edx, 4Eh ; 'N'
0x1800107a8  mov     rcx, [rcx+10h]
0x1800107ac  lea     r8, WPP_ac7e02637b6a307e043befe010ba928c_Traceguids
0x1800107b3  call    WPP_SF_d
0x1800107b8  mov     ebx, 80004005h
0x1800107bd  jmp     short loc_1800107FA
0x1800107bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800107c6  lea     rdx, WPP_GLOBAL_Control
0x1800107cd  cmp     rcx, rdx
0x1800107d0  jz      short loc_1800107F6
0x1800107d2  test    byte ptr [rcx+1Ch], 1
0x1800107d6  jz      short loc_1800107F6
0x1800107d8  cmp     byte ptr [rcx+19h], 2
0x1800107dc  jb      short loc_1800107F6
0x1800107de  mov     rcx, [rcx+10h]
0x1800107e2  lea     r8, WPP_ac7e02637b6a307e043befe010ba928c_Traceguids
0x1800107e9  mov     edx, 4Dh ; 'M'
0x1800107ee  mov     r9d, ebx
0x1800107f1  call    WPP_SF_d
0x1800107f6  bts     ebx, 1Ch
0x1800107fa  mov     [rbp+var_18], ebx
0x1800107fd  lea     rcx, [rbp+var_20]; this
0x180010801  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x180010806  mov     eax, ebx
0x180010808  add     rsp, 70h
0x18001080c  pop     r15
0x18001080e  pop     r14
0x180010810  pop     r12
0x180010812  pop     rdi
0x180010813  pop     rsi
0x180010814  pop     rbx
0x180010815  pop     rbp
0x180010816  retn
```
