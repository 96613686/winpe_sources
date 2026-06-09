# QueryDosNames(void *,_UNICODE_STRING const *,ATL::CHeapPtr<_MOUNTMGR_VOLUME_PATHS,ATL::CCRTAllocator> &,ulong *,ulong *)

- ea: `0x18000ed6c`
- end: `0x18000ef88`
- name: `?QueryDosNames@@YAJPEAXPEBU_UNICODE_STRING@@AEAV?$CHeapPtr@U_MOUNTMGR_VOLUME_PATHS@@VCCRTAllocator@ATL@@@ATL@@PEAK3@Z`
- size: `540`
- prototype: `__int64 __fastcall(HANDLE Handle, const void **, PVOID *, ULONG *, _DWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000f1dc`
- `0x180013b48`

## callees

- `0x1800032f8`
- `0x180006498`
- `0x180006688`
- `0x18000ed6c`
- `0x1800375e2`

## import_xrefs

- `msvcrt!realloc` at `0x18000eef0`
- `msvcrt!realloc` at `0x18000eef0`
- `msvcrt!malloc` at `0x18000ee3f`
- `msvcrt!malloc` at `0x18000ee3f`
- `msvcrt!free` at `0x18000ef63`
- `msvcrt!free` at `0x18000ef63`
- `ntdll!NtWaitForSingleObject` at `0x18000eec2`
- `ntdll!NtWaitForSingleObject` at `0x18000eec2`
- `ntdll!NtDeviceIoControlFile` at `0x18000eeab`
- `ntdll!NtDeviceIoControlFile` at `0x18000eeab`

## pseudocode

```c
__int64 __fastcall QueryDosNames(HANDLE Handle, const void **a2, PVOID *a3, ULONG *a4, _DWORD *a5)
{
  _QWORD *ThreadLocalStoragePointer; // rax
  USHORT Length; // cx
  __int64 v11; // rdx
  USHORT v12; // dx
  USHORT v13; // ax
  ULONG InputBufferLength; // esi
  _WORD *v15; // rax
  void *InputBuffer; // rbx
  void *v17; // rcx
  NTSTATUS Status; // edi
  unsigned int v19; // edi
  void *v20; // rax
  unsigned int v21; // edi
  const char *v23; // [rsp+50h] [rbp-21h] BYREF
  int v24; // [rsp+58h] [rbp-19h]
  USHORT v25; // [rsp+60h] [rbp-11h]
  USHORT v26; // [rsp+62h] [rbp-Fh]
  int v27; // [rsp+64h] [rbp-Dh]
  char *v28; // [rsp+68h] [rbp-9h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-1h] BYREF

  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  Length = GlobalIndentString.Length;
  v24 = 0;
  v23 = "QueryDosNames";
  v11 = ThreadLocalStoragePointer[tls_index];
  *(_QWORD *)(v11 + 16) = "QueryDosNames";
  v12 = ++*(_WORD *)(v11 + 8);
  v13 = Length;
  if ( v12 < Length )
  {
    v13 = v12;
    Length = v12;
  }
  v25 = v13;
  v27 = 0;
  v28 = off_180047060;
  v26 = Length;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"QueryDosNames");
  }
  InputBufferLength = *(unsigned __int16 *)a2 + 2;
  IoStatusBlock = 0;
  v15 = malloc(InputBufferLength);
  InputBuffer = v15;
  if ( v15 )
  {
    *a5 = 0;
    *v15 = *(_WORD *)a2;
    memcpy_0(v15 + 1, a2[1], *(unsigned __int16 *)a2);
    while ( 1 )
    {
      Status = NtDeviceIoControlFile(
                 Handle,
                 0,
                 0,
                 0,
                 &IoStatusBlock,
                 0x6D0034u,
                 InputBuffer,
                 InputBufferLength,
                 *a3,
                 *a4);
      if ( Status == 259 )
      {
        NtWaitForSingleObject(Handle, 0, 0);
        Status = IoStatusBlock.Status;
      }
      if ( Status == -1073741789 )
      {
        v19 = 2 * *a4;
      }
      else
      {
        if ( Status != -2147483643 )
        {
          if ( Status < 0 )
          {
            v21 = Status | 0x10000000;
            v24 = v21;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_ac7e02637b6a307e043befe010ba928c_Traceguids, v21);
            }
          }
          else
          {
            v21 = 0;
            *a5 = IoStatusBlock.Information;
          }
          v17 = InputBuffer;
          goto LABEL_27;
        }
        v19 = *(_DWORD *)*a3 + 4;
      }
      v20 = realloc(*a3, v19);
      if ( !v20 )
      {
        v17 = InputBuffer;
        goto LABEL_26;
      }
      *a3 = v20;
      *a4 = v19;
    }
  }
  v17 = 0;
LABEL_26:
  v21 = -2147024882;
  v24 = -2147024882;
LABEL_27:
  free(v17);
  CHResultImp::~CHResultImp((CHResultImp *)&v23);
  return v21;
}

```

## disassembly

```asm
0x18000ed6c  push    rbp
0x18000ed6e  push    rbx
0x18000ed6f  push    rsi
0x18000ed70  push    rdi
0x18000ed71  push    r12
0x18000ed73  push    r13
0x18000ed75  push    r14
0x18000ed77  push    r15
0x18000ed79  lea     rbp, [rsp-17h]
0x18000ed7e  sub     rsp, 88h
0x18000ed85  mov     rax, gs:58h
0x18000ed8e  mov     rdi, rdx
0x18000ed91  mov     r10d, cs:_tls_index
0x18000ed98  mov     r13, rcx
0x18000ed9b  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x18000eda2  mov     r14, r8
0x18000eda5  lea     r8, aQuerydosnames; "QueryDosNames"
0x18000edac  mov     [rbp+4Fh+var_68], 0
0x18000edb3  mov     r12, r9
0x18000edb6  mov     [rbp+4Fh+var_70], r8
0x18000edba  mov     rdx, [rax+r10*8]
0x18000edbe  mov     eax, 10h
0x18000edc3  mov     [rax+rdx], r8
0x18000edc7  mov     eax, 8
0x18000edcc  inc     word ptr [rax+rdx]
0x18000edd0  movzx   edx, word ptr [rax+rdx]
0x18000edd4  movzx   eax, cx
0x18000edd7  cmp     dx, cx
0x18000edda  cmovb   ax, dx
0x18000edde  cmovb   cx, dx
0x18000ede2  mov     [rbp+4Fh+var_60], ax
0x18000ede6  xor     eax, eax
0x18000ede8  mov     [rbp+4Fh+var_5C], eax
0x18000edeb  mov     rax, cs:off_180047060; "                                       "...
0x18000edf2  mov     [rbp+4Fh+var_58], rax
0x18000edf6  mov     [rbp+4Fh+var_5E], cx
0x18000edfa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ee01  lea     rax, WPP_GLOBAL_Control
0x18000ee08  cmp     rcx, rax
0x18000ee0b  jz      short loc_18000EE30
0x18000ee0d  test    byte ptr [rcx+1Ch], 1
0x18000ee11  jz      short loc_18000EE30
0x18000ee13  cmp     byte ptr [rcx+19h], 5
0x18000ee17  jb      short loc_18000EE30
0x18000ee19  mov     rcx, [rcx+10h]; LoggerHandle
0x18000ee1d  lea     r9, [rbp+4Fh+var_60]
0x18000ee21  mov     edx, 0Dh
0x18000ee26  mov     [rsp+0C0h+IoStatusBlock], r8; __int64
0x18000ee2b  call    WPP_SF_aZs
0x18000ee30  movzx   esi, word ptr [rdi]
0x18000ee33  xorps   xmm0, xmm0
0x18000ee36  add     esi, 2
0x18000ee39  mov     ecx, esi; Size
0x18000ee3b  movups  xmmword ptr [rbp+4Fh+var_50], xmm0
0x18000ee3f  call    cs:__imp_malloc
0x18000ee45  mov     rbx, rax
0x18000ee48  test    rax, rax
0x18000ee4b  jnz     short loc_18000EE54
0x18000ee4d  xor     ecx, ecx
0x18000ee4f  jmp     loc_18000EF5B
0x18000ee54  mov     r15, [rbp+4Fh+arg_20]
0x18000ee58  lea     rcx, [rbx+2]; void *
0x18000ee5c  mov     dword ptr [r15], 0
0x18000ee63  movzx   eax, word ptr [rdi]
0x18000ee66  mov     [rbx], ax
0x18000ee69  movzx   r8d, word ptr [rdi]; Size
0x18000ee6d  mov     rdx, [rdi+8]; Src
0x18000ee71  call    memcpy_0
0x18000ee76  mov     eax, [r12]
0x18000ee7a  xor     r9d, r9d; ApcContext
0x18000ee7d  mov     [rsp+0C0h+OutputBufferLength], eax; OutputBufferLength
0x18000ee81  xor     r8d, r8d; ApcRoutine
0x18000ee84  mov     rax, [r14]
0x18000ee87  xor     edx, edx; Event
0x18000ee89  mov     [rsp+0C0h+OutputBuffer], rax; OutputBuffer
0x18000ee8e  mov     rcx, r13; FileHandle
0x18000ee91  mov     [rsp+0C0h+InputBufferLength], esi; InputBufferLength
0x18000ee95  lea     rax, [rbp+4Fh+var_50]
0x18000ee99  mov     [rsp+0C0h+InputBuffer], rbx; InputBuffer
0x18000ee9e  mov     [rsp+0C0h+IoControlCode], 6D0034h; IoControlCode
0x18000eea6  mov     [rsp+0C0h+IoStatusBlock], rax; IoStatusBlock
0x18000eeab  call    cs:__imp_NtDeviceIoControlFile
0x18000eeb1  mov     edi, eax
0x18000eeb3  cmp     eax, 103h
0x18000eeb8  jnz     short loc_18000EECB
0x18000eeba  xor     r8d, r8d; Timeout
0x18000eebd  xor     edx, edx; Alertable
0x18000eebf  mov     rcx, r13; Handle
0x18000eec2  call    cs:__imp_NtWaitForSingleObject
0x18000eec8  mov     edi, dword ptr [rbp+4Fh+var_50]
0x18000eecb  cmp     edi, 0C0000023h
0x18000eed1  jz      short loc_18000EEE5
0x18000eed3  cmp     edi, 80000005h
0x18000eed9  jnz     short loc_18000EF07
0x18000eedb  mov     rax, [r14]
0x18000eede  mov     edi, [rax]
0x18000eee0  add     edi, 4
0x18000eee3  jmp     short loc_18000EEEB
0x18000eee5  mov     edi, [r12]
0x18000eee9  add     edi, edi
0x18000eeeb  mov     rcx, [r14]; Block
0x18000eeee  mov     edx, edi; Size
0x18000eef0  call    cs:__imp_realloc
0x18000eef6  test    rax, rax
0x18000eef9  jz      short loc_18000EF58
0x18000eefb  mov     [r14], rax
0x18000eefe  mov     [r12], edi
0x18000ef02  jmp     loc_18000EE76
0x18000ef07  test    edi, edi
0x18000ef09  js      short loc_18000EF15
0x18000ef0b  mov     eax, dword ptr [rbp+4Fh+var_50.Information]
0x18000ef0e  xor     edi, edi
0x18000ef10  mov     [r15], eax
0x18000ef13  jmp     short loc_18000EF53
0x18000ef15  bts     edi, 1Ch
0x18000ef19  mov     [rbp+4Fh+var_68], edi
0x18000ef1c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef23  lea     rax, WPP_GLOBAL_Control
0x18000ef2a  cmp     rcx, rax
0x18000ef2d  jz      short loc_18000EF53
0x18000ef2f  test    byte ptr [rcx+1Ch], 1
0x18000ef33  jz      short loc_18000EF53
0x18000ef35  cmp     byte ptr [rcx+19h], 2
0x18000ef39  jb      short loc_18000EF53
0x18000ef3b  mov     rcx, [rcx+10h]
0x18000ef3f  lea     r8, WPP_ac7e02637b6a307e043befe010ba928c_Traceguids
0x18000ef46  mov     edx, 18h
0x18000ef4b  mov     r9d, edi
0x18000ef4e  call    WPP_SF_d
0x18000ef53  mov     rcx, rbx
0x18000ef56  jmp     short loc_18000EF63
0x18000ef58  mov     rcx, rbx; Block
0x18000ef5b  mov     edi, 8007000Eh
0x18000ef60  mov     [rbp+4Fh+var_68], edi
0x18000ef63  call    cs:__imp_free
0x18000ef69  lea     rcx, [rbp+4Fh+var_70]; this
0x18000ef6d  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x18000ef72  mov     eax, edi
0x18000ef74  add     rsp, 88h
0x18000ef7b  pop     r15
0x18000ef7d  pop     r14
0x18000ef7f  pop     r13
0x18000ef81  pop     r12
0x18000ef83  pop     rdi
0x18000ef84  pop     rsi
0x18000ef85  pop     rbx
0x18000ef86  pop     rbp
0x18000ef87  retn
```
