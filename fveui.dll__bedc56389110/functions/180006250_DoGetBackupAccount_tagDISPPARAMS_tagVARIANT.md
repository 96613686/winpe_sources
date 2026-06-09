# DoGetBackupAccount(tagDISPPARAMS *,tagVARIANT *)

- ea: `0x180006250`
- end: `0x18000649a`
- name: `?DoGetBackupAccount@@YAJPEAUtagDISPPARAMS@@PEAUtagVARIANT@@@Z`
- size: `586`
- prototype: `__int64 __fastcall(struct tagDISPPARAMS *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001bb0`
- `0x1800037a0`
- `0x180006250`
- `0x18000b978`
- `0x18000b9bc`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180006454`
- `KERNEL32!HeapFree` at `0x18000646d`
- `KERNEL32!HeapFree` at `0x180006454`
- `KERNEL32!HeapFree` at `0x18000646d`
- `KERNEL32!HeapAlloc` at `0x1800062f0`
- `KERNEL32!HeapAlloc` at `0x18000638e`
- `KERNEL32!HeapAlloc` at `0x1800062f0`
- `KERNEL32!HeapAlloc` at `0x18000638e`
- `KERNEL32!GetProcessHeap` at `0x1800062d4`
- `KERNEL32!GetProcessHeap` at `0x18000637f`
- `KERNEL32!GetProcessHeap` at `0x180006446`
- `KERNEL32!GetProcessHeap` at `0x18000645f`
- `KERNEL32!GetProcessHeap` at `0x1800062d4`
- `KERNEL32!GetProcessHeap` at `0x18000637f`
- `KERNEL32!GetProcessHeap` at `0x180006446`
- `KERNEL32!GetProcessHeap` at `0x18000645f`
- `OLEAUT32!__imp_SysAllocString` at `0x180006410`
- `OLEAUT32!__imp_SysAllocString` at `0x180006410`
- `FVEAPI!FveCloseVolume` at `0x180006433`
- `FVEAPI!FveCloseVolume` at `0x180006433`
- `FVEAPI!FveOpenVolumeW` at `0x1800062a5`
- `FVEAPI!FveOpenVolumeW` at `0x1800062a5`
- `FVEAPI!FveGetRecoveryPasswordBackupAccountInformation` at `0x18000634e`
- `FVEAPI!FveGetRecoveryPasswordBackupAccountInformation` at `0x1800063c8`
- `FVEAPI!FveGetRecoveryPasswordBackupAccountInformation` at `0x18000634e`
- `FVEAPI!FveGetRecoveryPasswordBackupAccountInformation` at `0x1800063c8`
- `RPCRT4!UuidFromStringW` at `0x18000631d`
- `RPCRT4!UuidFromStringW` at `0x18000631d`

## pseudocode

```c
__int64 __fastcall DoGetBackupAccount(struct tagDISPPARAMS *a1, struct tagVARIANT *a2)
{
  VARIANTARG *rgvarg; // rcx
  OLECHAR *v4; // rdi
  LONGLONG llVal; // rcx
  unsigned __int16 *v7; // rsi
  RPC_STATUS v8; // ebx
  HANDLE ProcessHeap; // rax
  unsigned __int64 v10; // rbx
  RPC_STATUS RecoveryPasswordBackupAccountInformation; // eax
  SIZE_T v12; // rbx
  HANDLE v13; // rax
  BSTR v14; // rax
  int v15; // ecx
  HANDLE v16; // rax
  HANDLE v17; // rax
  __int64 v19; // [rsp+30h] [rbp-30h] BYREF
  __int64 v20; // [rsp+38h] [rbp-28h] BYREF
  unsigned __int64 v21; // [rsp+40h] [rbp-20h] BYREF
  UUID Uuid; // [rsp+48h] [rbp-18h] BYREF

  v19 = -1;
  rgvarg = a1->rgvarg;
  v4 = 0;
  v20 = 0;
  Uuid = 0;
  llVal = rgvarg->llVal;
  v21 = 0;
  v7 = 0;
  v8 = FveOpenVolumeW(llVal, 0, &v19);
  if ( v8 >= 0 )
  {
    v8 = StringCchLengthW(a1->rgvarg[1].bstrVal, 0x7FFFFFFFu, &v21);
    if ( v8 >= 0 )
    {
      ProcessHeap = GetProcessHeap();
      v10 = v21;
      v7 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 2 * v21 + 2);
      v8 = StringCchCopyW(v7, v10 + 1, a1->rgvarg[1].bstrVal);
      if ( v8 >= 0 )
      {
        v8 = UuidFromStringW(v7, &Uuid);
        if ( v8 >= 0 )
        {
          RecoveryPasswordBackupAccountInformation = FveGetRecoveryPasswordBackupAccountInformation(
                                                       v19,
                                                       &Uuid,
                                                       a1->rgvarg[2].uiVal,
                                                       0,
                                                       &v20,
                                                       0);
          v8 = RecoveryPasswordBackupAccountInformation;
          if ( RecoveryPasswordBackupAccountInformation == -2147024774 )
          {
            v12 = 2 * v20;
            v13 = GetProcessHeap();
            v4 = (OLECHAR *)HeapAlloc(v13, 8u, v12);
            if ( v4 )
            {
              v8 = FveGetRecoveryPasswordBackupAccountInformation(v19, &Uuid, a1->rgvarg[2].uiVal, v20, &v20, v4);
              if ( !v8 )
                goto LABEL_15;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  83,
                  &WPP_148a443baae43b032f4bebf0684096f9_Traceguids,
                  (unsigned int)v8);
              if ( v8 >= 0 )
              {
LABEL_15:
                a2->vt = 8;
                v14 = SysAllocString(v4);
                v15 = v8;
                a2->llVal = (LONGLONG)v14;
                if ( !v14 )
                  v15 = -2147024882;
                v8 = v15;
              }
            }
            else
            {
              v8 = -2147024882;
            }
          }
          else if ( RecoveryPasswordBackupAccountInformation == -2144272145 )
          {
            v8 = 0;
            a2->vt = 8;
            a2->llVal = 0;
          }
        }
      }
    }
  }
  if ( v19 != -1 )
  {
    FveCloseVolume(v19);
    v19 = -1;
  }
  if ( v4 )
  {
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v4);
  }
  if ( v7 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v7);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180006250  mov     [rsp-28h+arg_10], rbx
0x180006255  mov     [rsp-28h+arg_18], rsi
0x18000625a  push    rbp
0x18000625b  push    rdi
0x18000625c  push    r13
0x18000625e  push    r14
0x180006260  push    r15
0x180006262  mov     rbp, rsp
0x180006265  sub     rsp, 60h
0x180006269  mov     rax, cs:__security_cookie
0x180006270  xor     rax, rsp
0x180006273  mov     [rbp+var_8], rax
0x180006277  mov     r14, rcx
0x18000627a  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFFh
0x180006282  mov     rcx, [rcx]
0x180006285  lea     r8, [rbp+var_30]
0x180006289  xor     edi, edi
0x18000628b  xorps   xmm0, xmm0
0x18000628e  mov     r15, rdx
0x180006291  mov     [rbp+var_28], rdi
0x180006295  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x180006299  mov     rcx, [rcx+8]
0x18000629d  xor     edx, edx
0x18000629f  mov     [rbp+var_20], rdi
0x1800062a3  xor     esi, esi
0x1800062a5  call    cs:__imp_FveOpenVolumeW
0x1800062ab  mov     ebx, eax
0x1800062ad  test    eax, eax
0x1800062af  js      loc_180006429
0x1800062b5  mov     rcx, [r14]
0x1800062b8  lea     r8, [rbp+var_20]; unsigned __int64 *
0x1800062bc  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800062c1  mov     rcx, [rcx+20h]; unsigned __int16 *
0x1800062c5  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800062ca  mov     ebx, eax
0x1800062cc  test    eax, eax
0x1800062ce  js      loc_180006429
0x1800062d4  call    cs:__imp_GetProcessHeap
0x1800062da  mov     rbx, [rbp+var_20]
0x1800062de  lea     r13d, [rdi+8]
0x1800062e2  mov     edx, r13d; dwFlags
0x1800062e5  mov     rcx, rax; hHeap
0x1800062e8  lea     r8, ds:2[rbx*2]; dwBytes
0x1800062f0  call    cs:__imp_HeapAlloc
0x1800062f6  mov     r8, [r14]
0x1800062f9  lea     rdx, [rbx+1]; unsigned __int64
0x1800062fd  mov     rcx, rax; unsigned __int16 *
0x180006300  mov     rsi, rax
0x180006303  mov     r8, [r8+20h]; unsigned __int16 *
0x180006307  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000630c  mov     ebx, eax
0x18000630e  test    eax, eax
0x180006310  js      loc_180006429
0x180006316  lea     rdx, [rbp+Uuid]; Uuid
0x18000631a  mov     rcx, rsi; StringUuid
0x18000631d  call    cs:__imp_UuidFromStringW
0x180006323  mov     ebx, eax
0x180006325  test    eax, eax
0x180006327  js      loc_180006429
0x18000632d  mov     r8, [r14]
0x180006330  lea     rax, [rbp+var_28]
0x180006334  mov     rcx, [rbp+var_30]
0x180006338  lea     rdx, [rbp+Uuid]
0x18000633c  mov     [rsp+60h+var_38], rdi
0x180006341  xor     r9d, r9d
0x180006344  mov     [rsp+60h+var_40], rax
0x180006349  movzx   r8d, word ptr [r8+38h]
0x18000634e  call    cs:__imp_FveGetRecoveryPasswordBackupAccountInformation
0x180006354  mov     ebx, eax
0x180006356  cmp     eax, 8007007Ah
0x18000635b  jz      short loc_180006377
0x18000635d  cmp     eax, 803100EFh
0x180006362  jnz     loc_180006429
0x180006368  xor     ebx, ebx
0x18000636a  mov     [r15], r13w
0x18000636e  mov     [r15+8], rbx
0x180006372  jmp     loc_180006429
0x180006377  mov     rax, [rbp+var_28]
0x18000637b  lea     rbx, [rax+rax]
0x18000637f  call    cs:__imp_GetProcessHeap
0x180006385  mov     r8, rbx; dwBytes
0x180006388  mov     edx, r13d; dwFlags
0x18000638b  mov     rcx, rax; hHeap
0x18000638e  call    cs:__imp_HeapAlloc
0x180006394  mov     rdi, rax
0x180006397  test    rax, rax
0x18000639a  jnz     short loc_1800063A6
0x18000639c  mov     ebx, 8007000Eh
0x1800063a1  jmp     loc_180006429
0x1800063a6  mov     r8, [r14]
0x1800063a9  lea     rax, [rbp+var_28]
0x1800063ad  mov     r9, [rbp+var_28]
0x1800063b1  lea     rdx, [rbp+Uuid]
0x1800063b5  mov     rcx, [rbp+var_30]
0x1800063b9  mov     [rsp+60h+var_38], rdi
0x1800063be  movzx   r8d, word ptr [r8+38h]
0x1800063c3  mov     [rsp+60h+var_40], rax
0x1800063c8  call    cs:__imp_FveGetRecoveryPasswordBackupAccountInformation
0x1800063ce  mov     ebx, eax
0x1800063d0  test    eax, eax
0x1800063d2  jz      short loc_180006409
0x1800063d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800063db  lea     rax, WPP_GLOBAL_Control
0x1800063e2  cmp     rcx, rax
0x1800063e5  jz      short loc_180006405
0x1800063e7  test    byte ptr [rcx+1Ch], 40h
0x1800063eb  jz      short loc_180006405
0x1800063ed  mov     rcx, [rcx+10h]
0x1800063f1  lea     r8, WPP_148a443baae43b032f4bebf0684096f9_Traceguids
0x1800063f8  mov     edx, 53h ; 'S'
0x1800063fd  mov     r9d, ebx
0x180006400  call    WPP_SF_d
0x180006405  test    ebx, ebx
0x180006407  js      short loc_180006429
0x180006409  mov     rcx, rdi; psz
0x18000640c  mov     [r15], r13w
0x180006410  call    cs:__imp_SysAllocString
0x180006416  mov     ecx, ebx
0x180006418  mov     ebx, 8007000Eh
0x18000641d  test    rax, rax
0x180006420  mov     [r15+8], rax
0x180006424  cmovz   ecx, ebx
0x180006427  mov     ebx, ecx
0x180006429  mov     rcx, [rbp+var_30]
0x18000642d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180006431  jz      short loc_180006441
0x180006433  call    cs:__imp_FveCloseVolume
0x180006439  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFFh
0x180006441  test    rdi, rdi
0x180006444  jz      short loc_18000645A
0x180006446  call    cs:__imp_GetProcessHeap
0x18000644c  mov     r8, rdi; lpMem
0x18000644f  xor     edx, edx; dwFlags
0x180006451  mov     rcx, rax; hHeap
0x180006454  call    cs:__imp_HeapFree
0x18000645a  test    rsi, rsi
0x18000645d  jz      short loc_180006473
0x18000645f  call    cs:__imp_GetProcessHeap
0x180006465  mov     r8, rsi; lpMem
0x180006468  xor     edx, edx; dwFlags
0x18000646a  mov     rcx, rax; hHeap
0x18000646d  call    cs:__imp_HeapFree
0x180006473  mov     eax, ebx
0x180006475  mov     rcx, [rbp+var_8]
0x180006479  xor     rcx, rsp; StackCookie
0x18000647c  call    __security_check_cookie
0x180006481  lea     r11, [rsp+60h+var_s0]
0x180006486  mov     rbx, [r11+40h]
0x18000648a  mov     rsi, [r11+48h]
0x18000648e  mov     rsp, r11
0x180006491  pop     r15
0x180006493  pop     r14
0x180006495  pop     r13
0x180006497  pop     rdi
0x180006498  pop     rbp
0x180006499  retn
```
