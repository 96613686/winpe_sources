# CLONE_SYSPREP_ACTION_LIST::ExecuteIfPresent(CLONE_SYSPREP_ACTION_LIST *)

- ea: `0x180025a74`
- end: `0x180025b8d`
- name: `?ExecuteIfPresent@CLONE_SYSPREP_ACTION_LIST@@QEAAKPEAV1@@Z`
- size: `281`
- prototype: `__int64 __fastcall(wchar_t **this, wchar_t **)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180026914`

## callees

- `0x180025848`
- `0x180025890`
- `0x180025a74`
- `0x180025b94`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025af4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025af4`
- `WDSCORE!WdsSetupLogMessageW` at `0x180025b6d`
- `WDSCORE!WdsSetupLogMessageW` at `0x180025b6d`
- `WDSCORE!CurrentIP` at `0x180025afc`
- `WDSCORE!CurrentIP` at `0x180025afc`

## string_xrefs

- `0x180025b10`: `Skipping calling %ws:%hs because the component is not installed`

## pseudocode

```c
__int64 __fastcall CLONE_SYSPREP_ACTION_LIST::ExecuteIfPresent(wchar_t **this, wchar_t **a2)
{
  unsigned int v4; // r14d
  int i; // esi
  int v6; // edi
  int j; // ebx
  DWORD LastError; // edi
  __int64 v9; // rbx
  struct tagLOG_PARTIAL_MSG *v10; // rax

  v4 = 0;
  for ( i = 0; i < *((_DWORD *)this + 1024); ++i )
  {
    v6 = 0;
    for ( j = 0; j < *((_DWORD *)a2 + 1024); ++j )
    {
      if ( !CLONE_SYSPREP_MODULE::CompareSysprepModule(this[i], a2[j]) )
      {
        v6 = 1;
        break;
      }
    }
    if ( v6 )
    {
      v4 = CLONE_SYSPREP_MODULE::ExecuteModule((CLONE_SYSPREP_MODULE *)this[i]);
      if ( v4 )
        return v4;
    }
    else
    {
      LastError = GetLastError();
      v9 = CurrentIP();
      v10 = ConstructPartialMsgW(
              0x4000000,
              "Skipping calling %ws:%hs because the component is not installed",
              this[i],
              this[i] + 260);
      WdsSetupLogMessageW(
        v10,
        983040,
        L"D",
        0,
        535,
        L"ds\\ds\\src\\util\\clonelib\\clsysprep.cxx",
        L"CLONE_SYSPREP_ACTION_LIST::ExecuteIfPresent",
        v9,
        LastError,
        0,
        0);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180025a74  push    rbx
0x180025a76  push    rsi
0x180025a77  push    rdi
0x180025a78  push    r12
0x180025a7a  push    r13
0x180025a7c  push    r14
0x180025a7e  push    r15
0x180025a80  sub     rsp, 70h
0x180025a84  mov     r13, rdx
0x180025a87  mov     r15, rcx
0x180025a8a  xor     r14d, r14d
0x180025a8d  xor     esi, esi
0x180025a8f  mov     [rsp+0A8h+var_44], esi
0x180025a93  cmp     esi, [r15+1000h]
0x180025a9a  jge     loc_180025B7A
0x180025aa0  xor     edi, edi
0x180025aa2  xor     ebx, ebx
0x180025aa4  mov     [rsp+0A8h+var_48], ebx
0x180025aa8  cmp     ebx, [r13+1000h]
0x180025aaf  jge     short loc_180025ACC
0x180025ab1  movsxd  rdx, ebx
0x180025ab4  movsxd  rcx, esi
0x180025ab7  mov     rdx, [r13+rdx*8+0]; String2
0x180025abc  mov     rcx, [r15+rcx*8]; String1
0x180025ac0  call    ?CompareSysprepModule@CLONE_SYSPREP_MODULE@@SAHPEBV1@0@Z; CLONE_SYSPREP_MODULE::CompareSysprepModule(CLONE_SYSPREP_MODULE const *,CLONE_SYSPREP_MODULE const *)
0x180025ac5  test    eax, eax
0x180025ac7  jnz     short loc_180025AF0
0x180025ac9  lea     edi, [rax+1]
0x180025acc  movsxd  r12, esi
0x180025acf  test    edi, edi
0x180025ad1  jz      short loc_180025AF4
0x180025ad3  mov     rcx, [r15+r12*8]; this
0x180025ad7  call    ?ExecuteModule@CLONE_SYSPREP_MODULE@@QEAAKXZ; CLONE_SYSPREP_MODULE::ExecuteModule(void)
0x180025adc  mov     r14d, eax
0x180025adf  mov     [rsp+0A8h+var_40], eax
0x180025ae3  test    eax, eax
0x180025ae5  jnz     loc_180025B7A
0x180025aeb  jmp     loc_180025B73
0x180025af0  inc     ebx
0x180025af2  jmp     short loc_180025AA4
0x180025af4  call    cs:__imp_GetLastError
0x180025afa  mov     edi, eax
0x180025afc  call    cs:__imp_CurrentIP
0x180025b02  mov     rbx, rax
0x180025b05  mov     r8, [r15+r12*8]
0x180025b09  lea     r9, [r8+208h]
0x180025b10  lea     rdx, aSkippingCallin; "Skipping calling %ws:%hs because the co"...
0x180025b17  mov     ecx, 4000000h; unsigned int
0x180025b1c  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180025b21  mov     [rsp+0A8h+var_58], 0
0x180025b29  mov     [rsp+0A8h+var_60], 0
0x180025b32  mov     [rsp+0A8h+var_68], edi
0x180025b36  mov     [rsp+0A8h+var_70], rbx
0x180025b3b  lea     rcx, aCloneSysprepAc; "CLONE_SYSPREP_ACTION_LIST::ExecuteIfPre"...
0x180025b42  mov     [rsp+0A8h+var_78], rcx
0x180025b47  lea     rcx, aDsDsSrcUtilClo; "ds\\ds\\src\\util\\clonelib\\clsysprep."...
0x180025b4e  mov     [rsp+0A8h+var_80], rcx
0x180025b53  mov     [rsp+0A8h+var_88], 217h
0x180025b5b  xor     r9d, r9d
0x180025b5e  lea     r8, aD_0; "D"
0x180025b65  mov     edx, 0F0000h
0x180025b6a  mov     rcx, rax
0x180025b6d  call    cs:__imp_WdsSetupLogMessageW
0x180025b73  inc     esi
0x180025b75  jmp     loc_180025A8F
0x180025b7a  mov     eax, r14d
0x180025b7d  add     rsp, 70h
0x180025b81  pop     r15
0x180025b83  pop     r14
0x180025b85  pop     r13
0x180025b87  pop     r12
0x180025b89  pop     rdi
0x180025b8a  pop     rsi
0x180025b8b  pop     rbx
0x180025b8c  retn
0x18002c735  push    rbp
0x18002c737  sub     rsp, 60h
0x18002c73b  mov     rbp, rdx
0x18002c73e  add     rsp, 60h
0x18002c742  pop     rbp
0x18002c743  retn
```
