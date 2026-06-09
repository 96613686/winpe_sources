# BthServRestoreTemporaryScanState(void)

- ea: `0x18001ac64`
- end: `0x18001add5`
- name: `?BthServRestoreTemporaryScanState@@YAKXZ`
- size: `369`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000d498`

## callees

- `0x180012004`
- `0x1800120b8`
- `0x18001ac64`
- `0x18001addc`
- `0x18001afcc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ace3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ace3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001adab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001adab`

## pseudocode

```c
__int64 BthServRestoreTemporaryScanState(void)
{
  unsigned int v0; // edi
  char v1; // bl
  bool v2; // dl
  int v3; // edx
  int v4; // r8d
  _BYTE *v5; // rcx
  bool v6; // dl

  v0 = 0;
  v1 = 1;
  v2 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  EnterCriticalSection(&stru_1800470B0);
  if ( !dword_1800470D8 || (v0 = BthServSetDiscoverable(1)) == 0 )
  {
    if ( dword_1800470DC )
      v0 = BthServSetConnectable(1);
    goto LABEL_19;
  }
  v5 = WPP_GLOBAL_Control;
  v6 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
  if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v6,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
LABEL_19:
    v5 = WPP_GLOBAL_Control;
  }
  if ( v5 == (_BYTE *)&WPP_GLOBAL_Control || v5[25] < 4u )
    v1 = 0;
  if ( v1 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v3) = v1;
    LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)v5 + 2), v3, v4, *((_QWORD *)v5 + 5));
  }
  LeaveCriticalSection(&stru_1800470B0);
  return v0;
}

```

## disassembly

```asm
0x18001ac64  mov     rax, rsp
0x18001ac67  mov     [rax+8], rbx
0x18001ac6b  mov     [rax+10h], rbp
0x18001ac6f  mov     [rax+18h], rsi
0x18001ac73  mov     [rax+20h], rdi
0x18001ac77  push    r14
0x18001ac79  sub     rsp, 50h
0x18001ac7d  xor     edi, edi
0x18001ac7f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ac86  lea     rsi, WPP_GLOBAL_Control
0x18001ac8d  lea     ebx, [rdi+1]
0x18001ac90  cmp     rcx, rsi
0x18001ac93  jz      short loc_18001AC9F
0x18001ac95  cmp     byte ptr [rcx+19h], 4
0x18001ac99  jb      short loc_18001AC9F
0x18001ac9b  mov     dl, bl
0x18001ac9d  jmp     short loc_18001ACA1
0x18001ac9f  xor     dl, dl
0x18001aca1  lea     rbp, WPP_RECORDER_INITIALIZED
0x18001aca8  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18001acaf  lea     r14, WPP_1e105cb0c669395e076f5c19399c2c56_Traceguids
0x18001acb6  setnz   r8b
0x18001acba  test    dl, dl
0x18001acbc  jnz     short loc_18001ACC3
0x18001acbe  test    r8b, r8b
0x18001acc1  jz      short loc_18001ACDC
0x18001acc3  mov     r9, [rcx+28h]
0x18001acc7  mov     rcx, [rcx+10h]
0x18001accb  mov     [rsp+58h+var_20], r14
0x18001acd0  mov     [rsp+58h+var_28], 14h
0x18001acd7  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001acdc  lea     rcx, stru_1800470B0; lpCriticalSection
0x18001ace3  call    cs:__imp_EnterCriticalSection
0x18001acea  nop     dword ptr [rax+rax+00h]
0x18001acef  cmp     cs:dword_1800470D8, edi
0x18001acf5  jz      short loc_18001AD4B
0x18001acf7  mov     ecx, ebx; int
0x18001acf9  call    ?BthServSetDiscoverable@@YAKH@Z; BthServSetDiscoverable(int)
0x18001acfe  mov     edi, eax
0x18001ad00  test    eax, eax
0x18001ad02  jz      short loc_18001AD4B
0x18001ad04  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ad0b  cmp     rcx, rsi
0x18001ad0e  jz      short loc_18001AD1A
0x18001ad10  cmp     byte ptr [rcx+19h], 3
0x18001ad14  jb      short loc_18001AD1A
0x18001ad16  mov     dl, bl
0x18001ad18  jmp     short loc_18001AD1C
0x18001ad1a  xor     dl, dl
0x18001ad1c  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18001ad23  setnz   r8b
0x18001ad27  test    dl, dl
0x18001ad29  jnz     short loc_18001AD30
0x18001ad2b  test    r8b, r8b
0x18001ad2e  jz      short loc_18001AD64
0x18001ad30  mov     r9, [rcx+28h]
0x18001ad34  mov     rcx, [rcx+10h]
0x18001ad38  mov     [rsp+58h+var_20], r14
0x18001ad3d  mov     [rsp+58h+var_28], 15h
0x18001ad44  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001ad49  jmp     short loc_18001AD5D
0x18001ad4b  cmp     cs:dword_1800470DC, 0
0x18001ad52  jz      short loc_18001AD5D
0x18001ad54  mov     ecx, ebx; int
0x18001ad56  call    ?BthServSetConnectable@@YAKH@Z; BthServSetConnectable(int)
0x18001ad5b  mov     edi, eax
0x18001ad5d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ad64  cmp     rcx, rsi
0x18001ad67  jz      short loc_18001AD6F
0x18001ad69  cmp     byte ptr [rcx+19h], 4
0x18001ad6d  jnb     short loc_18001AD71
0x18001ad6f  xor     bl, bl
0x18001ad71  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18001ad78  setnz   r8b
0x18001ad7c  test    bl, bl
0x18001ad7e  jnz     short loc_18001AD85
0x18001ad80  test    r8b, r8b
0x18001ad83  jz      short loc_18001ADA4
0x18001ad85  mov     r9, [rcx+28h]
0x18001ad89  mov     dl, bl
0x18001ad8b  mov     rcx, [rcx+10h]
0x18001ad8f  mov     [rsp+58h+var_10], edi
0x18001ad93  mov     [rsp+58h+var_20], r14
0x18001ad98  mov     [rsp+58h+var_28], 16h
0x18001ad9f  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18001ada4  lea     rcx, stru_1800470B0; lpCriticalSection
0x18001adab  call    cs:__imp_LeaveCriticalSection
0x18001adb2  nop     dword ptr [rax+rax+00h]
0x18001adb7  mov     rbx, [rsp+58h+arg_0]
0x18001adbc  mov     eax, edi
0x18001adbe  mov     rdi, [rsp+58h+arg_18]
0x18001adc3  mov     rbp, [rsp+58h+arg_8]
0x18001adc8  mov     rsi, [rsp+58h+arg_10]
0x18001adcd  add     rsp, 50h
0x18001add1  pop     r14
0x18001add3  retn
```
