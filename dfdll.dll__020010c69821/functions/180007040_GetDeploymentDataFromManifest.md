# GetDeploymentDataFromManifest

- ea: `0x180007040`
- end: `0x180007126`
- name: `GetDeploymentDataFromManifest`
- size: `230`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 *, unsigned int *, unsigned __int16 *, unsigned int *, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callees

- `0x180007040`
- `0x180008a14`
- `0x180008d34`
- `0x18000dadc`
- `0x180012bd0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetDeploymentDataFromManifest(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int *a4,
        unsigned __int16 *a5,
        unsigned int *a6,
        unsigned __int16 *a7,
        unsigned int *a8,
        unsigned __int16 *a9,
        unsigned int *a10)
{
  int DeploymentDataFromManifest; // ebx
  _BYTE v16[240]; // [rsp+70h] [rbp-148h] BYREF

  Dfdll::CSubscription::CSubscription((Dfdll::CSubscription *)v16);
  DeploymentDataFromManifest = Dfdll::CSubscription::LoadDeploymentDataFromManifest(
                                 (Dfdll::CSubscription *)v16,
                                 a1,
                                 a2,
                                 a3,
                                 a4,
                                 a5,
                                 a6,
                                 a7,
                                 a8,
                                 a9,
                                 a10);
  if ( DeploymentDataFromManifest >= 0 )
    DeploymentDataFromManifest = 0;
  Dfdll::CSubscription::~CSubscription((Dfdll::CSubscription *)v16);
  return (unsigned int)DeploymentDataFromManifest;
}

```

## disassembly

```asm
0x180007040  push    rbx
0x180007042  push    rbp
0x180007043  push    rsi
0x180007044  push    rdi
0x180007045  push    r12
0x180007047  push    r13
0x180007049  push    r14
0x18000704b  push    r15
0x18000704d  sub     rsp, 178h
0x180007054  mov     rax, cs:__security_cookie
0x18000705b  xor     rax, rsp
0x18000705e  mov     [rsp+1B8h+var_58], rax
0x180007066  mov     [rsp+1B8h+var_158], r9
0x18000706b  mov     [rsp+1B8h+var_150], r8
0x180007070  mov     r13, rdx
0x180007073  mov     r12, rcx
0x180007076  mov     r15, [rsp+1B8h+arg_20]
0x18000707e  mov     r14, [rsp+1B8h+arg_28]
0x180007086  mov     rbp, [rsp+1B8h+arg_30]
0x18000708e  mov     rsi, [rsp+1B8h+arg_38]
0x180007096  mov     rdi, [rsp+1B8h+arg_40]
0x18000709e  mov     rbx, [rsp+1B8h+arg_48]
0x1800070a6  lea     rcx, [rsp+1B8h+var_148]; this
0x1800070ab  call    ??0CSubscription@Dfdll@@QEAA@XZ; Dfdll::CSubscription::CSubscription(void)
0x1800070b0  nop
0x1800070b1  mov     [rsp+1B8h+var_168], rbx; unsigned int *
0x1800070b6  mov     [rsp+1B8h+var_170], rdi; unsigned __int16 *
0x1800070bb  mov     [rsp+1B8h+var_178], rsi; unsigned int *
0x1800070c0  mov     [rsp+1B8h+var_180], rbp; unsigned __int16 *
0x1800070c5  mov     [rsp+1B8h+var_188], r14; unsigned int *
0x1800070ca  mov     [rsp+1B8h+var_190], r15; unsigned __int16 *
0x1800070cf  mov     rax, [rsp+1B8h+var_158]
0x1800070d4  mov     [rsp+1B8h+var_198], rax; unsigned int *
0x1800070d9  mov     r9, [rsp+1B8h+var_150]; unsigned __int16 *
0x1800070de  mov     r8, r13; unsigned __int16 *
0x1800070e1  mov     rdx, r12; unsigned __int16 *
0x1800070e4  lea     rcx, [rsp+1B8h+var_148]; this
0x1800070e9  call    ?LoadDeploymentDataFromManifest@CSubscription@Dfdll@@QEAAJPEBG0PEAGPEAK121212@Z; Dfdll::CSubscription::LoadDeploymentDataFromManifest(ushort const *,ushort const *,ushort *,ulong *,ushort *,ulong *,ushort *,ulong *,ushort *,ulong *)
0x1800070ee  mov     ebx, eax
0x1800070f0  test    eax, eax
0x1800070f2  js      short loc_1800070F6
0x1800070f4  xor     ebx, ebx
0x1800070f6  lea     rcx, [rsp+1B8h+var_148]; this
0x1800070fb  call    ??1CSubscription@Dfdll@@QEAA@XZ; Dfdll::CSubscription::~CSubscription(void)
0x180007100  mov     eax, ebx
0x180007102  mov     rcx, [rsp+1B8h+var_58]
0x18000710a  xor     rcx, rsp; StackCookie
0x18000710d  call    __security_check_cookie
0x180007112  add     rsp, 178h
0x180007119  pop     r15
0x18000711b  pop     r14
0x18000711d  pop     r13
0x18000711f  pop     r12
0x180007121  pop     rdi
0x180007122  pop     rsi
0x180007123  pop     rbp
0x180007124  pop     rbx
0x180007125  retn
```
