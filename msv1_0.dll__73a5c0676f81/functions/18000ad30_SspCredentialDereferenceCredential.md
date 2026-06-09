# SspCredentialDereferenceCredential

- ea: `0x18000ad30`
- end: `0x18000afa5`
- name: `SspCredentialDereferenceCredential`
- size: `629`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `9`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000a020`
- `0x18000a380`
- `0x18000a570`
- `0x180014dc0`
- `0x1800157b0`
- `0x180025ff0`
- `0x1800268dc`
- `0x18002ae74`
- `0x18002ba90`

## callees

- `0x180006c50`
- `0x18000ad30`
- `0x18002ee3c`
- `0x180030844`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000aeca`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000ad6b`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000ad6b`
- `ntdll!NtClose` at `0x18000aeb5`
- `ntdll!NtClose` at `0x18000aeb5`
- `ntdll!RtlReleaseResource` at `0x18000ad91`
- `ntdll!RtlReleaseResource` at `0x18000addf`
- `ntdll!RtlReleaseResource` at `0x18000af61`
- `ntdll!RtlReleaseResource` at `0x18000ad91`
- `ntdll!RtlReleaseResource` at `0x18000addf`
- `ntdll!RtlReleaseResource` at `0x18000af61`
- `LSASRV!LsaIFreeSupplementalTokenInfo` at `0x18000ae6f`
- `LSASRV!LsaIFreeSupplementalTokenInfo` at `0x18000ae6f`

## pseudocode

```c
void __fastcall SspCredentialDereferenceCredential(void ***a1)
{
  int v2; // edi
  void **v3; // rax
  void **v4; // rcx
  void **v5; // rcx
  void **v6; // rax
  void **v7; // rcx
  void **v8; // rcx
  void **v9; // rcx
  void **v10; // rcx
  void **v11; // rcx
  void **v12; // rcx
  __int64 v13; // rcx

  if ( _InterlockedExchangeAdd((volatile signed __int32 *)a1 + 4, 0xFFFFFFFF) == 1 )
  {
    v2 = 0;
    RtlAcquireResourceExclusive(&SspCredentialCritSect, 1u);
    if ( *((_DWORD *)a1 + 9) == 1097101891 && (v2 = 1, *((_DWORD *)a1 + 4)) )
    {
      RtlReleaseResource(&SspCredentialCritSect);
    }
    else if ( v2 )
    {
      v3 = *a1;
      if ( (*a1)[1] != a1 || (v4 = a1[1], *v4 != a1) )
        __fastfail(3u);
      *v4 = v3;
      v3[1] = v4;
      *((_BYTE *)a1 + 96) = 1;
      *((_DWORD *)a1 + 9) = 1147433539;
      RtlReleaseResource(&SspCredentialCritSect);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_589a2f61f8ac3b6ff36408465b886615_Traceguids, a1);
      v5 = a1[14];
      if ( v5 )
        NtClose(v5);
      v6 = a1[11];
      if ( v6 )
      {
        v13 = *((unsigned __int16 *)a1 + 41);
        if ( *((_WORD *)a1 + 41) )
        {
          do
          {
            *(_BYTE *)v6 = 0;
            v6 = (void **)((char *)v6 + 1);
            --v13;
          }
          while ( v13 );
        }
        NtLmFree(a1[11]);
      }
      v7 = a1[7];
      if ( v7 )
        NtLmFree(v7);
      v8 = a1[9];
      if ( v8 )
        NtLmFree(v8);
      v9 = a1[21];
      if ( v9 )
      {
        memset_0(v9, 0, *((unsigned __int16 *)a1 + 81));
        NtLmFree(a1[21]);
      }
      v10 = a1[17];
      if ( v10 )
        NtLmFree(v10);
      v11 = a1[19];
      if ( v11 )
        NtLmFree(v11);
      v12 = a1[13];
      if ( v12 )
        LsaIFreeSupplementalTokenInfo(v12);
      memset_0(a1, 0, 0xB0u);
      if ( NtLmState == 1 )
        ((void (__fastcall *)(void ***))LsaFunctions->FreePrivateHeap)(a1);
      else
        LocalFree(a1);
    }
    else
    {
      RtlReleaseResource(&SspCredentialCritSect);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_589a2f61f8ac3b6ff36408465b886615_Traceguids, a1);
    }
  }
}

```

## disassembly

```asm
0x18000ad30  mov     [rsp+arg_10], rbx
0x18000ad35  mov     [rsp+arg_0], rcx
0x18000ad3a  push    rdi
0x18000ad3b  sub     rsp, 30h
0x18000ad3f  mov     rbx, rcx
0x18000ad42  mov     eax, 0FFFFFFFFh
0x18000ad47  lock xadd [rcx+10h], eax
0x18000ad4c  cmp     eax, 1
0x18000ad4f  jz      short loc_18000AD5C
0x18000ad51  mov     rbx, [rsp+38h+arg_10]
0x18000ad56  add     rsp, 30h
0x18000ad5a  pop     rdi
0x18000ad5b  retn
0x18000ad5c  xor     edi, edi
0x18000ad5e  mov     [rsp+38h+var_18], edi
0x18000ad62  mov     dl, 1; Wait
0x18000ad64  lea     rcx, ?SspCredentialCritSect@@3U_RTL_RESOURCE@@A; Resource
0x18000ad6b  call    cs:__imp_RtlAcquireResourceExclusive
0x18000ad71  nop
0x18000ad72  cmp     dword ptr [rbx+24h], 41647243h
0x18000ad79  jnz     short loc_18000AD99
0x18000ad7b  mov     edi, 1
0x18000ad80  mov     [rsp+38h+var_18], edi
0x18000ad84  cmp     dword ptr [rbx+10h], 0
0x18000ad88  jbe     short loc_18000AD99
0x18000ad8a  lea     rcx, ?SspCredentialCritSect@@3U_RTL_RESOURCE@@A; Resource
0x18000ad91  call    cs:__imp_RtlReleaseResource
0x18000ad97  jmp     short loc_18000AD51
0x18000ad99  jmp     short loc_18000ADA4
0x18000ad9b  mov     rbx, [rsp+38h+arg_0]
0x18000ada0  mov     edi, [rsp+38h+var_18]
0x18000ada4  test    edi, edi
0x18000ada6  jz      loc_18000AF5A
0x18000adac  mov     rax, [rbx]
0x18000adaf  cmp     [rax+8], rbx
0x18000adb3  jnz     loc_18000AEAE
0x18000adb9  mov     rcx, [rbx+8]
0x18000adbd  cmp     [rcx], rbx
0x18000adc0  jnz     loc_18000AEAE
0x18000adc6  mov     [rcx], rax
0x18000adc9  mov     [rax+8], rcx
0x18000adcd  mov     byte ptr [rbx+60h], 1
0x18000add1  mov     dword ptr [rbx+24h], 44647243h
0x18000add8  lea     rcx, ?SspCredentialCritSect@@3U_RTL_RESOURCE@@A; Resource
0x18000addf  call    cs:__imp_RtlReleaseResource
0x18000ade5  lea     rax, WPP_GLOBAL_Control
0x18000adec  mov     rcx, cs:WPP_GLOBAL_Control
0x18000adf3  cmp     rcx, rax
0x18000adf6  jz      short loc_18000AE02
0x18000adf8  test    byte ptr [rcx+1Ch], 20h
0x18000adfc  jnz     loc_18000AEF5
0x18000ae02  mov     rcx, [rbx+70h]; Handle
0x18000ae06  test    rcx, rcx
0x18000ae09  jnz     loc_18000AEB5
0x18000ae0f  mov     rax, [rbx+58h]
0x18000ae13  test    rax, rax
0x18000ae16  jnz     loc_18000AED1
0x18000ae1c  mov     rcx, [rbx+38h]
0x18000ae20  test    rcx, rcx
0x18000ae23  jnz     loc_18000AF12
0x18000ae29  mov     rcx, [rbx+48h]
0x18000ae2d  test    rcx, rcx
0x18000ae30  jnz     loc_18000AF1C
0x18000ae36  mov     rcx, [rbx+0A8h]; void *
0x18000ae3d  test    rcx, rcx
0x18000ae40  jnz     loc_18000AF26
0x18000ae46  mov     rcx, [rbx+88h]
0x18000ae4d  test    rcx, rcx
0x18000ae50  jnz     loc_18000AF46
0x18000ae56  mov     rcx, [rbx+98h]
0x18000ae5d  test    rcx, rcx
0x18000ae60  jnz     loc_18000AF50
0x18000ae66  mov     rcx, [rbx+68h]
0x18000ae6a  test    rcx, rcx
0x18000ae6d  jz      short loc_18000AE75
0x18000ae6f  call    cs:__imp_LsaIFreeSupplementalTokenInfo
0x18000ae75  xor     edx, edx; Val
0x18000ae77  mov     r8d, 0B0h; Size
0x18000ae7d  mov     rcx, rbx; void *
0x18000ae80  call    memset_0
0x18000ae85  mov     rcx, rbx
0x18000ae88  cmp     cs:NtLmState, 1
0x18000ae8f  jnz     short loc_18000AEC0
0x18000ae91  mov     rax, cs:LsaFunctions
0x18000ae98  mov     rax, [rax+188h]
0x18000ae9f  mov     rbx, [rsp+38h+arg_10]
0x18000aea4  add     rsp, 30h
0x18000aea8  pop     rdi
0x18000aea9  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000aeae  mov     ecx, 3
0x18000aeb3  int     29h; Win8: RtlFailFast(ecx)
0x18000aeb5  call    cs:__imp_NtClose
0x18000aebb  jmp     loc_18000AE0F
0x18000aec0  mov     rbx, [rsp+38h+arg_10]
0x18000aec5  add     rsp, 30h
0x18000aec9  pop     rdi
0x18000aeca  jmp     cs:__imp_LocalFree
0x18000aed1  movzx   ecx, word ptr [rbx+52h]
0x18000aed5  test    rcx, rcx
0x18000aed8  jz      short loc_18000AEE7
0x18000aeda  mov     byte ptr [rax], 0
0x18000aedd  lea     rax, [rax+1]
0x18000aee1  sub     rcx, 1
0x18000aee5  jnz     short loc_18000AEDA
0x18000aee7  mov     rcx, [rbx+58h]
0x18000aeeb  call    NtLmFree
0x18000aef0  jmp     loc_18000AE1C
0x18000aef5  mov     edx, 13h
0x18000aefa  mov     r9, rbx
0x18000aefd  lea     r8, WPP_589a2f61f8ac3b6ff36408465b886615_Traceguids
0x18000af04  mov     rcx, [rcx+10h]
0x18000af08  call    WPP_SF_q
0x18000af0d  jmp     loc_18000AE02
0x18000af12  call    NtLmFree
0x18000af17  jmp     loc_18000AE29
0x18000af1c  call    NtLmFree
0x18000af21  jmp     loc_18000AE36
0x18000af26  movzx   r8d, word ptr [rbx+0A2h]; Size
0x18000af2e  xor     edx, edx; Val
0x18000af30  call    memset_0
0x18000af35  mov     rcx, [rbx+0A8h]
0x18000af3c  call    NtLmFree
0x18000af41  jmp     loc_18000AE46
0x18000af46  call    NtLmFree
0x18000af4b  jmp     loc_18000AE56
0x18000af50  call    NtLmFree
0x18000af55  jmp     loc_18000AE66
0x18000af5a  lea     rcx, ?SspCredentialCritSect@@3U_RTL_RESOURCE@@A; Resource
0x18000af61  call    cs:__imp_RtlReleaseResource
0x18000af67  lea     rax, WPP_GLOBAL_Control
0x18000af6e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000af75  cmp     rcx, rax
0x18000af78  jz      loc_18000AD51
0x18000af7e  test    byte ptr [rcx+1Ch], 1
0x18000af82  jz      loc_18000AD51
0x18000af88  mov     edx, 12h
0x18000af8d  mov     r9, rbx
0x18000af90  lea     r8, WPP_589a2f61f8ac3b6ff36408465b886615_Traceguids
0x18000af97  mov     rcx, [rcx+10h]
0x18000af9b  call    WPP_SF_q
0x18000afa0  jmp     loc_18000AD51
```
