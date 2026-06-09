# BuildLocalKey(void *,MASTERKEY_STORED *,uint,uint)

- ea: `0x18002ac04`
- end: `0x18002ad48`
- name: `?BuildLocalKey@@YAKPEAXPEAUMASTERKEY_STORED@@II@Z`
- size: `324`
- prototype: `__int64 __fastcall(void *, struct MASTERKEY_STORED *, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e9c0`
- `0x1800180cc`
- `0x18002ea4c`

## callees

- `0x180007f10`
- `0x180011014`
- `0x180012258`
- `0x18001d810`
- `0x18002ac04`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x18002ac61`
- `bcrypt!BCryptGenRandom` at `0x18002ac61`
- `ntdll!RtlNtStatusToDosError` at `0x18002ac73`
- `ntdll!RtlNtStatusToDosError` at `0x18002ac73`

## string_xrefs

- `0x18002ac87`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`

## pseudocode

```c
__int64 __fastcall BuildLocalKey(void *a1, struct MASTERKEY_STORED *a2, unsigned int a3, unsigned int a4)
{
  __int64 v4; // rsi
  __int64 v9; // rdi
  int v10; // eax
  ULONG v11; // eax
  ULONG v12; // ebx
  __int64 v13; // r9
  UCHAR *v14; // rax
  unsigned __int8 *v15; // rax
  size_t v17; // [rsp+40h] [rbp-79h]
  unsigned int v18; // [rsp+50h] [rbp-69h] BYREF
  unsigned int v19; // [rsp+54h] [rbp-65h] BYREF
  UCHAR pbBuffer[16]; // [rsp+58h] [rbp-61h] BYREF
  __int128 v21; // [rsp+68h] [rbp-51h]
  unsigned __int8 v22[64]; // [rsp+80h] [rbp-39h] BYREF

  v4 = 64;
  v18 = 0;
  v19 = 64;
  v9 = 32;
  *(_OWORD *)pbBuffer = 0;
  v21 = 0;
  v10 = BCryptGenRandom(0, pbBuffer, 0x20u, 2u);
  if ( v10 >= 0 )
  {
    v12 = 0;
    if ( !(unsigned int)GetLocalKeyUserEncryptionKey(a1, a2, v22, &v19, &v18) )
      goto LABEL_8;
    LODWORD(v17) = 32;
    v11 = EncryptMasterKeyToStorage(a2, 1u, a3, a4, v22, v19, v18, pbBuffer, v17);
    v12 = v11;
    if ( !v11 )
    {
      v12 = 0;
      goto LABEL_8;
    }
    v13 = 2626;
  }
  else
  {
    v11 = RtlNtStatusToDosError(v10);
    v12 = v11;
    v13 = 2588;
  }
  DebugTraceError(v11, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", v13);
LABEL_8:
  v14 = pbBuffer;
  do
  {
    *v14++ = 0;
    --v9;
  }
  while ( v9 );
  v15 = v22;
  do
  {
    *v15++ = 0;
    --v4;
  }
  while ( v4 );
  return v12;
}

```

## disassembly

```asm
0x18002ac04  push    rbp
0x18002ac06  push    rbx
0x18002ac07  push    rsi
0x18002ac08  push    rdi
0x18002ac09  push    r12
0x18002ac0b  push    r13
0x18002ac0d  push    r14
0x18002ac0f  push    r15
0x18002ac11  lea     rbp, [rsp-1Fh]
0x18002ac16  sub     rsp, 0D8h
0x18002ac1d  mov     rax, cs:__security_cookie
0x18002ac24  xor     rax, rsp
0x18002ac27  mov     [rbp+57h+var_50], rax
0x18002ac2b  mov     esi, 40h ; '@'
0x18002ac30  mov     [rbp+57h+var_C0], 0
0x18002ac37  xorps   xmm0, xmm0
0x18002ac3a  mov     [rbp+57h+var_BC], esi
0x18002ac3d  mov     r13d, r9d
0x18002ac40  mov     r12d, r8d
0x18002ac43  mov     r14, rdx
0x18002ac46  mov     r15, rcx
0x18002ac49  lea     edi, [rsi-20h]
0x18002ac4c  xor     ecx, ecx; hAlgorithm
0x18002ac4e  mov     r8d, edi; cbBuffer
0x18002ac51  lea     r9d, [rsi-3Eh]; dwFlags
0x18002ac55  lea     rdx, [rbp+57h+pbBuffer]; pbBuffer
0x18002ac59  movups  xmmword ptr [rbp+57h+pbBuffer], xmm0
0x18002ac5d  movups  [rbp+57h+var_A8], xmm0
0x18002ac61  call    cs:__imp_BCryptGenRandom
0x18002ac68  nop     dword ptr [rax+rax+00h]
0x18002ac6d  test    eax, eax
0x18002ac6f  jns     short loc_18002AC9E
0x18002ac71  mov     ecx, eax; Status
0x18002ac73  call    cs:__imp_RtlNtStatusToDosError
0x18002ac7a  nop     dword ptr [rax+rax+00h]
0x18002ac7f  mov     ebx, eax
0x18002ac81  mov     r9d, 0A1Ch
0x18002ac87  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002ac8e  mov     ecx, eax
0x18002ac90  lea     rdx, aDwlasterror; "dwLastError"
0x18002ac97  call    DebugTraceError
0x18002ac9c  jmp     short loc_18002AD05
0x18002ac9e  lea     rax, [rbp+57h+var_C0]
0x18002aca2  mov     rdx, r14; struct MASTERKEY_STORED *
0x18002aca5  lea     r9, [rbp+57h+var_BC]; unsigned int *
0x18002aca9  mov     [rsp+110h+var_F0], rax; unsigned int *
0x18002acae  lea     r8, [rbp+57h+var_90]; unsigned __int8 *
0x18002acb2  mov     rcx, r15; void *
0x18002acb5  xor     ebx, ebx
0x18002acb7  call    ?GetLocalKeyUserEncryptionKey@@YAHPEAXPEAUMASTERKEY_STORED@@PEAEPEAK3@Z; GetLocalKeyUserEncryptionKey(void *,MASTERKEY_STORED *,uchar *,ulong *,ulong *)
0x18002acbc  test    eax, eax
0x18002acbe  jz      short loc_18002AD05
0x18002acc0  mov     dword ptr [rsp+110h+var_D0], edi; size_t
0x18002acc4  lea     rax, [rbp+57h+pbBuffer]
0x18002acc8  mov     [rsp+110h+var_D8], rax; unsigned __int8 *
0x18002accd  lea     edx, [rbx+1]; unsigned int
0x18002acd0  mov     eax, [rbp+57h+var_C0]
0x18002acd3  mov     r9d, r13d; unsigned int
0x18002acd6  mov     [rsp+110h+var_E0], eax; unsigned int
0x18002acda  mov     r8d, r12d; unsigned int
0x18002acdd  mov     eax, [rbp+57h+var_BC]
0x18002ace0  mov     rcx, r14; struct MASTERKEY_STORED *
0x18002ace3  mov     [rsp+110h+var_E8], eax; unsigned int
0x18002ace7  lea     rax, [rbp+57h+var_90]
0x18002aceb  mov     [rsp+110h+var_F0], rax; unsigned __int8 *
0x18002acf0  call    ?EncryptMasterKeyToStorage@@YAKPEAUMASTERKEY_STORED@@KIIPEAEKK1K@Z; EncryptMasterKeyToStorage(MASTERKEY_STORED *,ulong,uint,uint,uchar *,ulong,ulong,uchar *,ulong)
0x18002acf5  mov     ebx, eax
0x18002acf7  test    eax, eax
0x18002acf9  jz      short loc_18002AD03
0x18002acfb  mov     r9d, 0A42h
0x18002ad01  jmp     short loc_18002AC87
0x18002ad03  xor     ebx, ebx
0x18002ad05  lea     rax, [rbp+57h+pbBuffer]
0x18002ad09  mov     byte ptr [rax], 0
0x18002ad0c  inc     rax
0x18002ad0f  sub     rdi, 1
0x18002ad13  jnz     short loc_18002AD09
0x18002ad15  lea     rax, [rbp+57h+var_90]
0x18002ad19  mov     byte ptr [rax], 0
0x18002ad1c  inc     rax
0x18002ad1f  sub     rsi, 1
0x18002ad23  jnz     short loc_18002AD19
0x18002ad25  mov     eax, ebx
0x18002ad27  mov     rcx, [rbp+57h+var_50]
0x18002ad2b  xor     rcx, rsp; StackCookie
0x18002ad2e  call    __security_check_cookie
0x18002ad33  add     rsp, 0D8h
0x18002ad3a  pop     r15
0x18002ad3c  pop     r14
0x18002ad3e  pop     r13
0x18002ad40  pop     r12
0x18002ad42  pop     rdi
0x18002ad43  pop     rsi
0x18002ad44  pop     rbx
0x18002ad45  pop     rbp
0x18002ad46  retn
```
