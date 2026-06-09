# DhcpQueryLeaseInfoEx

- ea: `0x180001010`
- end: `0x180001235`
- name: `DhcpQueryLeaseInfoEx`
- size: `549`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180001010`
- `0x180002620`
- `0x1800027b0`
- `0x180002ef0`
- `0x1800048c0`
- `0x180005162`
- `0x18000f4ec`
- `0x1800127f0`
- `0x180012850`
- `0x180012ad0`
- `0x180012d20`

## import_xrefs

- `RPCRT4!I_RpcExceptionFilter` at `0x180010b3e`
- `RPCRT4!I_RpcExceptionFilter` at `0x180010b3e`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x1800010ea`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000112a`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000114d`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x1800010ea`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000112a`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000114d`

## pseudocode

```c
__int64 __fastcall DhcpQueryLeaseInfoEx(__int64 a1, _OWORD *a2, _DWORD *a3)
{
  unsigned int LeaseInfo; // edi
  __int64 v7; // rcx
  LPWSTR CommandLineW; // rax
  int v9; // ecx
  LPWSTR v10; // rax
  int v11; // ecx
  _QWORD v13[3]; // [rsp+38h] [rbp-C0h] BYREF
  _OWORD v14[7]; // [rsp+50h] [rbp-A8h] BYREF
  __int64 v15; // [rsp+C0h] [rbp-38h]

  v13[1] = a1;
  v13[2] = a2;
  v13[0] = 0;
  memset_0(v14, 0, 0x78u);
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_S(1028, 147, WPP_e15037783097355a5233924022d92169_Traceguids, a1);
  if ( a2 )
    memset_0(a2, 0, 0x78u);
  if ( a3 )
    *a3 = 0;
  if ( a1 )
  {
    if ( a2 )
    {
      if ( a3 )
      {
        LeaseInfo = DhcpAdapterNameToIfId(a1, v13);
        if ( !LeaseInfo )
        {
          if ( (xmmword_18001E1E0 & 0x10) != 0 )
          {
            CommandLineW = GetCommandLineW();
            WPP_SF_SS(v9, 148, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, a1, (__int64)CommandLineW);
          }
          LeaseInfo = RpcCliQueryLeaseInfo(v7, v13, v14, a3);
          if ( (xmmword_18001E1E0 & 0x10) != 0 )
          {
            v10 = GetCommandLineW();
            WPP_SF_DSS(
              v11,
              149,
              (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids,
              LeaseInfo,
              a1,
              (__int64)v10);
          }
          if ( !LeaseInfo )
          {
            *a2 = v14[0];
            a2[1] = v14[1];
            a2[2] = v14[2];
            a2[3] = v14[3];
            a2[4] = v14[4];
            a2[5] = v14[5];
            a2[6] = v14[6];
            *((_QWORD *)a2 + 14) = v15;
            memset_0(v14, 0, 0x78u);
          }
        }
      }
      else
      {
        LeaseInfo = 87;
      }
    }
    else
    {
      LeaseInfo = 87;
    }
  }
  else
  {
    LeaseInfo = 87;
  }
  DhcpFreeLeaseInfo(v14);
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_SD(1028, 150, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, a1, LeaseInfo);
  return LeaseInfo;
}

```

## disassembly

```asm
0x180001010  mov     [rsp+arg_18], rbx
0x180001015  push    rsi
0x180001016  push    rdi
0x180001017  push    r14
0x180001019  sub     rsp, 0E0h
0x180001020  mov     rax, cs:__security_cookie
0x180001027  xor     rax, rsp
0x18000102a  mov     [rsp+0F8h+var_28], rax
0x180001032  mov     r14, r8
0x180001035  mov     rbx, rdx
0x180001038  mov     rsi, rcx
0x18000103b  mov     [rsp+0F8h+var_B8], rcx
0x180001040  mov     [rsp+0F8h+var_B0], rdx
0x180001045  xor     edi, edi
0x180001047  mov     [rsp+0F8h+var_C0], rdi
0x18000104c  xor     edx, edx; Val
0x18000104e  mov     r8d, 78h ; 'x'; Size
0x180001054  lea     rcx, [rsp+0F8h+var_A8]; void *
0x180001059  call    memset_0
0x18000105e  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180001065  jz      short loc_180001080
0x180001067  mov     edx, 93h
0x18000106c  mov     ecx, 404h
0x180001071  mov     r9, rsi
0x180001074  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000107b  call    WPP_SF_S
0x180001080  test    rbx, rbx
0x180001083  jz      short loc_180001095
0x180001085  xor     edx, edx; Val
0x180001087  mov     r8d, 78h ; 'x'; Size
0x18000108d  mov     rcx, rbx; void *
0x180001090  call    memset_0
0x180001095  test    r14, r14
0x180001098  jz      short loc_18000109D
0x18000109a  mov     [r14], edi
0x18000109d  test    rsi, rsi
0x1800010a0  jnz     short loc_1800010AC
0x1800010a2  mov     edi, 57h ; 'W'
0x1800010a7  jmp     loc_1800011DF
0x1800010ac  test    rbx, rbx
0x1800010af  jnz     short loc_1800010BB
0x1800010b1  mov     edi, 57h ; 'W'
0x1800010b6  jmp     loc_1800011DF
0x1800010bb  test    r14, r14
0x1800010be  jnz     short loc_1800010CA
0x1800010c0  mov     edi, 57h ; 'W'
0x1800010c5  jmp     loc_1800011DF
0x1800010ca  lea     rdx, [rsp+0F8h+var_C0]
0x1800010cf  mov     rcx, rsi
0x1800010d2  call    DhcpAdapterNameToIfId
0x1800010d7  mov     edi, eax
0x1800010d9  test    eax, eax
0x1800010db  jnz     loc_1800011DF
0x1800010e1  test    byte ptr cs:xmmword_18001E1E0, 10h
0x1800010e8  jz      short loc_18000110A
0x1800010ea  call    cs:__imp_GetCommandLineW
0x1800010f0  mov     edx, 94h
0x1800010f5  mov     [rsp+0F8h+var_D8], rax
0x1800010fa  mov     r9, rsi
0x1800010fd  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180001104  call    WPP_SF_SS
0x180001109  nop
0x18000110a  mov     r9, r14
0x18000110d  lea     r8, [rsp+0F8h+var_A8]
0x180001112  lea     rdx, [rsp+0F8h+var_C0]
0x180001117  call    RpcCliQueryLeaseInfo
0x18000111c  mov     edi, eax
0x18000111e  mov     [rsp+0F8h+var_C8], eax
0x180001122  jmp     short loc_180001144
0x180001124  mov     edi, eax
0x180001126  mov     [rsp+0F8h+var_C8], eax
0x18000112a  call    cs:__imp_GetCommandLineW
0x180001130  mov     rdx, rax
0x180001133  mov     ecx, edi
0x180001135  call    TraceRpcException
0x18000113a  mov     rsi, [rsp+0F8h+var_B8]
0x18000113f  mov     rbx, [rsp+0F8h+var_B0]
0x180001144  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000114b  jz      short loc_180001171
0x18000114d  call    cs:__imp_GetCommandLineW
0x180001153  mov     edx, 95h
0x180001158  mov     [rsp+0F8h+var_D0], rax
0x18000115d  mov     [rsp+0F8h+var_D8], rsi
0x180001162  mov     r9d, edi
0x180001165  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000116c  call    WPP_SF_DSS
0x180001171  test    edi, edi
0x180001173  jnz     short loc_1800011DF
0x180001175  movaps  xmm0, [rsp+0F8h+var_A8]
0x18000117a  movups  xmmword ptr [rbx], xmm0
0x18000117d  movaps  xmm1, [rsp+0F8h+var_98]
0x180001182  movups  xmmword ptr [rbx+10h], xmm1
0x180001186  movaps  xmm0, [rsp+0F8h+var_88]
0x18000118b  movups  xmmword ptr [rbx+20h], xmm0
0x18000118f  movaps  xmm1, [rsp+0F8h+var_78]
0x180001197  movups  xmmword ptr [rbx+30h], xmm1
0x18000119b  movaps  xmm0, [rsp+0F8h+var_68]
0x1800011a3  movups  xmmword ptr [rbx+40h], xmm0
0x1800011a7  movaps  xmm1, [rsp+0F8h+var_58]
0x1800011af  movups  xmmword ptr [rbx+50h], xmm1
0x1800011b3  movaps  xmm0, [rsp+0F8h+var_48]
0x1800011bb  movups  xmmword ptr [rbx+60h], xmm0
0x1800011bf  movsd   xmm1, [rsp+0F8h+var_38]
0x1800011c8  movsd   qword ptr [rbx+70h], xmm1
0x1800011cd  xor     edx, edx; Val
0x1800011cf  mov     r8d, 78h ; 'x'; Size
0x1800011d5  lea     rcx, [rsp+0F8h+var_A8]; void *
0x1800011da  call    memset_0
0x1800011df  lea     rcx, [rsp+0F8h+var_A8]; void *
0x1800011e4  call    DhcpFreeLeaseInfo
0x1800011e9  test    byte ptr cs:xmmword_18001E1E0, 10h
0x1800011f0  jz      short loc_18000120F
0x1800011f2  mov     edx, 96h
0x1800011f7  mov     ecx, 404h
0x1800011fc  mov     dword ptr [rsp+0F8h+var_D8], edi
0x180001200  mov     r9, rsi
0x180001203  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000120a  call    WPP_SF_SD
0x18000120f  mov     eax, edi
0x180001211  mov     rcx, [rsp+0F8h+var_28]
0x180001219  xor     rcx, rsp; StackCookie
0x18000121c  call    __security_check_cookie
0x180001221  mov     rbx, [rsp+0F8h+arg_18]
0x180001229  add     rsp, 0E0h
0x180001230  pop     r14
0x180001232  pop     rdi
0x180001233  pop     rsi
0x180001234  retn
0x180010b30  push    rbp
0x180010b32  sub     rsp, 30h
0x180010b36  mov     rbp, rdx
0x180010b39  mov     rcx, [rcx]
0x180010b3c  mov     ecx, [rcx]; ExceptionCode
0x180010b3e  call    cs:__imp_I_RpcExceptionFilter
0x180010b44  nop
0x180010b45  add     rsp, 30h
0x180010b49  pop     rbp
0x180010b4a  retn
```
