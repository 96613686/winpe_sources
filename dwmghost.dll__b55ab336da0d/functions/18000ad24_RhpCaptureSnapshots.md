# RhpCaptureSnapshots

- ea: `0x18000ad24`
- end: `0x18000ae4b`
- name: `RhpCaptureSnapshots`
- size: `295`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000a9c4`

## callees

- `0x180001962`
- `0x18000ad24`

## import_xrefs

- `ntdll!RtlQueryResourcePolicy` at `0x18000adab`
- `ntdll!RtlQueryResourcePolicy` at `0x18000adab`
- `ntdll!NtClose` at `0x18000ae23`
- `ntdll!NtClose` at `0x18000ae23`
- `ntdll!PssNtCaptureSnapshot` at `0x18000ae15`
- `ntdll!PssNtCaptureSnapshot` at `0x18000ae15`
- `ntdll!NtOpenProcess` at `0x18000ade6`
- `ntdll!NtOpenProcess` at `0x18000ade6`

## pseudocode

```c
NTSTATUS __fastcall RhpCaptureSnapshots(_QWORD *a1, _OWORD *a2, __m128i *a3, __int64 a4, int *a5)
{
  NTSTATUS result; // eax
  __m128i si128; // xmm1
  int *v10; // rbx
  void *v11; // rdx
  int v12; // eax
  void *v13; // rcx
  int v14; // ebx
  void *ProcessHandle; // [rsp+20h] [rbp-20h] BYREF
  __int64 v16; // [rsp+28h] [rbp-18h] BYREF
  _CLIENT_ID ClientId; // [rsp+30h] [rbp-10h] BYREF
  int v18; // [rsp+78h] [rbp+38h] BYREF

  ProcessHandle = 0;
  v16 = 0;
  v18 = 0;
  ClientId = 0;
  result = (unsigned int)memset_0(a1, 0, 0x80u);
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v10 = a5;
  *a2 = 0;
  *a3 = si128;
  a3[1] = si128;
  a3[2] = si128;
  a3[3] = si128;
  if ( *v10 )
  {
    result = RtlQueryResourcePolicy(0, 0, &v18, 4);
    if ( result < 0 || v18 > 10 )
    {
      ClientId.UniqueProcess = (HANDLE)*v10;
      ClientId.UniqueThread = 0;
      result = NtOpenProcess(&ProcessHandle, 0x4D0u, (POBJECT_ATTRIBUTES)&ObjectAttributes, &ClientId);
      a3->m128i_i32[0] = result;
      if ( result >= 0 )
      {
        v11 = ProcessHandle;
        *a1 = 0;
        v16 = 0;
        v12 = PssNtCaptureSnapshot(&v16, v11, 3690994175LL, 1048607);
        v13 = ProcessHandle;
        v14 = v12;
        a3->m128i_i32[0] = v12;
        result = NtClose(v13);
        if ( v14 >= 0 )
        {
          result = v16;
          *a1 = v16;
          *(_BYTE *)a2 = 8;
        }
      }
    }
    else
    {
      a3->m128i_i32[0] = -1073741801;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000ad24  mov     [rsp-18h+arg_0], rbx
0x18000ad29  mov     [rsp-18h+arg_8], rsi
0x18000ad2e  mov     [rsp-18h+arg_18], r9d
0x18000ad33  push    rbp
0x18000ad34  push    rdi
0x18000ad35  push    r14
0x18000ad37  mov     rbp, rsp
0x18000ad3a  sub     rsp, 40h
0x18000ad3e  mov     rdi, r8
0x18000ad41  mov     [rbp+ProcessHandle], 0
0x18000ad49  mov     r14, rdx
0x18000ad4c  mov     [rbp+var_18], 0
0x18000ad54  xorps   xmm0, xmm0
0x18000ad57  mov     [rbp+arg_18], 0
0x18000ad5e  xor     edx, edx; Val
0x18000ad60  mov     r8d, 80h; Size
0x18000ad66  movups  xmmword ptr [rbp+ClientId.UniqueProcess], xmm0
0x18000ad6a  mov     rsi, rcx
0x18000ad6d  call    memset_0
0x18000ad72  movdqa  xmm1, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18000ad7a  xorps   xmm0, xmm0
0x18000ad7d  mov     rbx, [rbp+arg_20]
0x18000ad81  movups  xmmword ptr [r14], xmm0
0x18000ad85  movups  xmmword ptr [rdi], xmm1
0x18000ad88  movups  xmmword ptr [rdi+10h], xmm1
0x18000ad8c  movups  xmmword ptr [rdi+20h], xmm1
0x18000ad90  movups  xmmword ptr [rdi+30h], xmm1
0x18000ad94  cmp     dword ptr [rbx], 0
0x18000ad97  jz      loc_18000AE38
0x18000ad9d  mov     r9d, 4
0x18000ada3  lea     r8, [rbp+arg_18]
0x18000ada7  xor     edx, edx
0x18000ada9  xor     ecx, ecx
0x18000adab  call    cs:__imp_RtlQueryResourcePolicy
0x18000adb1  test    eax, eax
0x18000adb3  js      short loc_18000ADC3
0x18000adb5  cmp     [rbp+arg_18], 0Ah
0x18000adb9  jg      short loc_18000ADC3
0x18000adbb  mov     dword ptr [rdi], 0C0000017h
0x18000adc1  jmp     short loc_18000AE38
0x18000adc3  movsxd  rax, dword ptr [rbx]
0x18000adc6  lea     r9, [rbp+ClientId]; ClientId
0x18000adca  lea     r8, ObjectAttributes; ObjectAttributes
0x18000add1  mov     [rbp+ClientId.UniqueProcess], rax
0x18000add5  mov     edx, 4D0h; DesiredAccess
0x18000adda  mov     [rbp+ClientId.UniqueThread], 0
0x18000ade2  lea     rcx, [rbp+ProcessHandle]; ProcessHandle
0x18000ade6  call    cs:__imp_NtOpenProcess
0x18000adec  mov     [rdi], eax
0x18000adee  test    eax, eax
0x18000adf0  js      short loc_18000AE38
0x18000adf2  mov     rdx, [rbp+ProcessHandle]
0x18000adf6  lea     rcx, [rbp+var_18]
0x18000adfa  mov     r9d, 10001Fh
0x18000ae00  mov     qword ptr [rsi], 0
0x18000ae07  mov     r8d, 0DC0019FFh
0x18000ae0d  mov     [rbp+var_18], 0
0x18000ae15  call    cs:__imp_PssNtCaptureSnapshot
0x18000ae1b  mov     rcx, [rbp+ProcessHandle]; Handle
0x18000ae1f  mov     ebx, eax
0x18000ae21  mov     [rdi], eax
0x18000ae23  call    cs:__imp_NtClose
0x18000ae29  test    ebx, ebx
0x18000ae2b  js      short loc_18000AE38
0x18000ae2d  mov     rax, [rbp+var_18]
0x18000ae31  mov     [rsi], rax
0x18000ae34  mov     byte ptr [r14], 8
0x18000ae38  mov     rbx, [rsp+40h+arg_0]
0x18000ae3d  mov     rsi, [rsp+40h+arg_8]
0x18000ae42  add     rsp, 40h
0x18000ae46  pop     r14
0x18000ae48  pop     rdi
0x18000ae49  pop     rbp
0x18000ae4a  retn
```
