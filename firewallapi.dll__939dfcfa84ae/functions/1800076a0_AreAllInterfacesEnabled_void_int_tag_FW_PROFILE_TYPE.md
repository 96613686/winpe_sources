# AreAllInterfacesEnabled(void *,int *,_tag_FW_PROFILE_TYPE)

- ea: `0x1800076a0`
- end: `0x1800079f9`
- name: `?AreAllInterfacesEnabled@@YAJPEAXPEAHW4_tag_FW_PROFILE_TYPE@@@Z`
- size: `857`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180006874`

## callees

- `0x180005e0c`
- `0x1800076a0`
- `0x180009210`
- `0x1800294b0`
- `0x18003336c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180007722`
- `ntdll!EtwEventWrite` at `0x1800077b1`
- `ntdll!EtwEventWrite` at `0x180007722`
- `ntdll!EtwEventWrite` at `0x1800077b1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180007744`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180007744`
- `fwbase!FwBaseAlloc` at `0x1800077e8`
- `fwbase!FwBaseAlloc` at `0x1800077e8`
- `fwbase!FwBaseFree` at `0x180007843`
- `fwbase!FwBaseFree` at `0x180007919`
- `fwbase!FwBaseFree` at `0x180007976`
- `fwbase!FwBaseFree` at `0x180007843`
- `fwbase!FwBaseFree` at `0x180007919`
- `fwbase!FwBaseFree` at `0x180007976`

## pseudocode

```c
__int64 __fastcall AreAllInterfacesEnabled(__int64 a1, _DWORD *a2, unsigned int a3)
{
  unsigned int v6; // esi
  FwPolicy2 *v7; // rax
  unsigned int v8; // ebp
  __int64 v9; // rcx
  _DWORD *v10; // rdi
  int v11; // ebx
  int v13[2]; // [rsp+40h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_7a1bb6b0559931aedf4a075b0cecbabd_Traceguids);
  *a2 = 0;
  v6 = 0;
  v7 = WPP_GLOBAL_Control;
  v8 = 0;
  v9 = g_Provider;
  v10 = 0;
  v13[0] = 0;
  while ( 1 )
  {
    v13[1] = 0;
    if ( v9 )
    {
      EtwEventWrite(v9, MPS_CLNT_API_Enter_GetConfig, 0, 0);
      v7 = WPP_GLOBAL_Control;
    }
    if ( v7 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)v7 + 2), 105, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
    GetTickCount64();
    v11 = Int_FWGetOrSetConfig(1u, a1, 0xFu, a3, 1, (__int64)v10, v13);
    if ( !v11 )
      goto LABEL_11;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        106,
        WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids,
        (unsigned int)v11);
LABEL_11:
      v7 = WPP_GLOBAL_Control;
    }
    v9 = g_Provider;
    if ( g_Provider )
    {
      EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_GetConfig, 0, 0);
      v7 = WPP_GLOBAL_Control;
      v9 = g_Provider;
    }
    if ( !v11 )
      goto LABEL_20;
    if ( v11 != 234 )
      break;
    if ( v10 )
      FwBaseFree(v10);
    v10 = (_DWORD *)FwBaseAlloc((unsigned int)v13[0]);
    if ( !v10 )
    {
      v6 = -2147024882;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_428964b663db31776494a5e8e5edd24b_Traceguids, 2147942414LL);
        goto LABEL_38;
      }
      goto LABEL_39;
    }
    v7 = WPP_GLOBAL_Control;
    v9 = g_Provider;
LABEL_20:
    if ( v8 <= 5 && !v11 )
      goto LABEL_22;
    ++v8;
  }
  if ( v11 > 0 )
    v6 = (unsigned __int16)v11 | 0x80070000;
  else
    v6 = v11;
  if ( v7 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v7 + 2), 14, WPP_428964b663db31776494a5e8e5edd24b_Traceguids, v6);
    v7 = WPP_GLOBAL_Control;
  }
  if ( v10 )
  {
    FwBaseFree(v10);
LABEL_38:
    v7 = WPP_GLOBAL_Control;
  }
LABEL_39:
  v10 = 0;
LABEL_22:
  if ( v6 == -2147024894 )
  {
    *a2 = 1;
    v6 = 0;
  }
  else if ( (v6 & 0x80000000) != 0 )
  {
    if ( v7 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)v7 + 2), 33, WPP_7a1bb6b0559931aedf4a075b0cecbabd_Traceguids, v6);
  }
  else
  {
    *a2 = *v10 == 0;
  }
  FwBaseFree(v10);
  return v6;
}

```

## disassembly

```asm
0x1800076a0  mov     [rsp+arg_18], rbx
0x1800076a5  push    rbp
0x1800076a6  push    rsi
0x1800076a7  push    rdi
0x1800076a8  push    r12
0x1800076aa  push    r13
0x1800076ac  push    r14
0x1800076ae  push    r15
0x1800076b0  sub     rsp, 50h
0x1800076b4  mov     rax, cs:__security_cookie
0x1800076bb  xor     rax, rsp
0x1800076be  mov     [rsp+88h+var_40], rax
0x1800076c3  mov     r12d, r8d
0x1800076c6  mov     r14, rdx
0x1800076c9  mov     r15, rcx
0x1800076cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800076d3  lea     rbx, WPP_GLOBAL_Control
0x1800076da  cmp     rcx, rbx
0x1800076dd  jz      short loc_1800076E9
0x1800076df  test    byte ptr [rcx+1Ch], 8
0x1800076e3  jnz     loc_18000793F
0x1800076e9  xor     r13d, r13d
0x1800076ec  mov     [r14], r13d
0x1800076ef  mov     esi, r13d
0x1800076f2  mov     rax, cs:WPP_GLOBAL_Control
0x1800076f9  mov     ebp, r13d
0x1800076fc  mov     rcx, cs:g_Provider
0x180007703  mov     edi, r13d
0x180007706  mov     [rsp+88h+var_48], r13d
0x18000770b  mov     [rsp+88h+var_44], r13d
0x180007710  test    rcx, rcx
0x180007713  jz      short loc_180007735
0x180007715  xor     r9d, r9d
0x180007718  lea     rdx, MPS_CLNT_API_Enter_GetConfig
0x18000771f  xor     r8d, r8d
0x180007722  call    cs:__imp_EtwEventWrite
0x180007729  nop     dword ptr [rax+rax+00h]
0x18000772e  mov     rax, cs:WPP_GLOBAL_Control
0x180007735  cmp     rax, rbx
0x180007738  jz      short loc_180007744
0x18000773a  test    byte ptr [rax+1Ch], 8
0x18000773e  jnz     loc_180007959
0x180007744  call    cs:__imp_GetTickCount64
0x18000774b  nop     dword ptr [rax+rax+00h]
0x180007750  lea     rax, [rsp+88h+var_44]
0x180007755  mov     r9d, r12d
0x180007758  mov     [rsp+88h+var_50], rax
0x18000775d  mov     r8d, 0Fh
0x180007763  lea     rax, [rsp+88h+var_48]
0x180007768  mov     rdx, r15
0x18000776b  mov     [rsp+88h+var_58], rax
0x180007770  mov     ecx, 1
0x180007775  mov     [rsp+88h+var_60], rdi
0x18000777a  mov     [rsp+88h+var_68], 1
0x180007782  call    Int_FWGetOrSetConfig
0x180007787  mov     ebx, eax
0x180007789  test    eax, eax
0x18000778b  jnz     loc_180007885
0x180007791  mov     rax, cs:WPP_GLOBAL_Control
0x180007798  mov     rcx, cs:g_Provider
0x18000779f  test    rcx, rcx
0x1800077a2  jz      short loc_1800077CB
0x1800077a4  xor     r9d, r9d
0x1800077a7  lea     rdx, MPS_CLNT_API_Exit_GetConfig
0x1800077ae  xor     r8d, r8d
0x1800077b1  call    cs:__imp_EtwEventWrite
0x1800077b8  nop     dword ptr [rax+rax+00h]
0x1800077bd  mov     rax, cs:WPP_GLOBAL_Control
0x1800077c4  mov     rcx, cs:g_Provider
0x1800077cb  test    ebx, ebx
0x1800077cd  jz      short loc_18000780E
0x1800077cf  cmp     ebx, 0EAh
0x1800077d5  jnz     loc_1800078D2
0x1800077db  test    rdi, rdi
0x1800077de  jnz     loc_180007973
0x1800077e4  mov     ecx, [rsp+88h+var_48]
0x1800077e8  call    cs:__imp_FwBaseAlloc
0x1800077ef  nop     dword ptr [rax+rax+00h]
0x1800077f4  mov     rdi, rax
0x1800077f7  test    rax, rax
0x1800077fa  jz      loc_180007987
0x180007800  mov     rax, cs:WPP_GLOBAL_Control
0x180007807  mov     rcx, cs:g_Provider
0x18000780e  cmp     ebp, 5
0x180007811  ja      short loc_180007877
0x180007813  mov     edx, esi
0x180007815  test    ebx, ebx
0x180007817  jnz     short loc_180007877
0x180007819  test    edx, edx
0x18000781b  js      loc_180007911
0x180007821  cmp     esi, 80070002h
0x180007827  jz      loc_1800078C3
0x18000782d  test    esi, esi
0x18000782f  js      loc_1800079C2
0x180007835  mov     edx, r13d
0x180007838  cmp     [rdi], edx
0x18000783a  setbe   dl
0x18000783d  mov     [r14], edx
0x180007840  mov     rcx, rdi
0x180007843  call    cs:__imp_FwBaseFree
0x18000784a  nop     dword ptr [rax+rax+00h]
0x18000784f  mov     eax, esi
0x180007851  mov     rcx, [rsp+88h+var_40]
0x180007856  xor     rcx, rsp; StackCookie
0x180007859  call    __security_check_cookie
0x18000785e  mov     rbx, [rsp+88h+arg_18]
0x180007866  add     rsp, 50h
0x18000786a  pop     r15
0x18000786c  pop     r14
0x18000786e  pop     r13
0x180007870  pop     r12
0x180007872  pop     rdi
0x180007873  pop     rsi
0x180007874  pop     rbp
0x180007875  retn
0x180007877  inc     ebp
0x180007879  lea     rbx, WPP_GLOBAL_Control
0x180007880  jmp     loc_18000770B
0x180007885  mov     rax, cs:WPP_GLOBAL_Control
0x18000788c  lea     rcx, WPP_GLOBAL_Control
0x180007893  cmp     rax, rcx
0x180007896  jz      loc_180007798
0x18000789c  test    byte ptr [rax+1Ch], 1
0x1800078a0  jz      loc_180007798
0x1800078a6  mov     rcx, [rax+10h]
0x1800078aa  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x1800078b1  mov     edx, 6Ah ; 'j'
0x1800078b6  mov     r9d, ebx
0x1800078b9  call    WPP_SF_d
0x1800078be  jmp     loc_180007791
0x1800078c3  mov     dword ptr [r14], 1
0x1800078ca  mov     esi, r13d
0x1800078cd  jmp     loc_180007840
0x1800078d2  test    ebx, ebx
0x1800078d4  jg      short loc_180007934
0x1800078d6  mov     esi, ebx
0x1800078d8  test    esi, esi
0x1800078da  jns     loc_18000780E
0x1800078e0  lea     rcx, WPP_GLOBAL_Control
0x1800078e7  cmp     rax, rcx
0x1800078ea  jz      short loc_180007911
0x1800078ec  test    byte ptr [rax+1Ch], 1
0x1800078f0  jz      short loc_180007911
0x1800078f2  mov     rcx, [rax+10h]
0x1800078f6  lea     r8, WPP_428964b663db31776494a5e8e5edd24b_Traceguids
0x1800078fd  mov     edx, 0Eh
0x180007902  mov     r9d, esi
0x180007905  call    WPP_SF_d
0x18000790a  mov     rax, cs:WPP_GLOBAL_Control
0x180007911  test    rdi, rdi
0x180007914  jz      short loc_18000792C
0x180007916  mov     rcx, rdi
0x180007919  call    cs:__imp_FwBaseFree
0x180007920  nop     dword ptr [rax+rax+00h]
0x180007925  mov     rax, cs:WPP_GLOBAL_Control
0x18000792c  mov     rdi, r13
0x18000792f  jmp     loc_180007821
0x180007934  movzx   esi, bx
0x180007937  or      esi, 80070000h
0x18000793d  jmp     short loc_1800078D8
0x18000793f  mov     rcx, [rcx+10h]
0x180007943  lea     r8, WPP_7a1bb6b0559931aedf4a075b0cecbabd_Traceguids
0x18000794a  mov     edx, 20h ; ' '
0x18000794f  call    WPP_SF_
0x180007954  jmp     loc_1800076E9
0x180007959  mov     rcx, [rax+10h]
0x18000795d  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180007964  mov     edx, 69h ; 'i'
0x180007969  call    WPP_SF_
0x18000796e  jmp     loc_180007744
0x180007973  mov     rcx, rdi
0x180007976  call    cs:__imp_FwBaseFree
0x18000797d  nop     dword ptr [rax+rax+00h]
0x180007982  jmp     loc_1800077E4
0x180007987  mov     esi, 8007000Eh
0x18000798c  mov     rax, cs:WPP_GLOBAL_Control
0x180007993  lea     rcx, WPP_GLOBAL_Control
0x18000799a  cmp     rax, rcx
0x18000799d  jz      short loc_18000792C
0x18000799f  test    byte ptr [rax+1Ch], 1
0x1800079a3  jz      short loc_18000792C
0x1800079a5  mov     rcx, [rax+10h]
0x1800079a9  lea     r8, WPP_428964b663db31776494a5e8e5edd24b_Traceguids
0x1800079b0  mov     edx, 0Dh
0x1800079b5  mov     r9d, esi
0x1800079b8  call    WPP_SF_d
0x1800079bd  jmp     loc_180007925
0x1800079c2  lea     rcx, WPP_GLOBAL_Control
0x1800079c9  cmp     rax, rcx
0x1800079cc  jz      loc_180007840
0x1800079d2  test    byte ptr [rax+1Ch], 1
0x1800079d6  jz      loc_180007840
0x1800079dc  mov     rcx, [rax+10h]
0x1800079e0  lea     r8, WPP_7a1bb6b0559931aedf4a075b0cecbabd_Traceguids
0x1800079e7  mov     edx, 21h ; '!'
0x1800079ec  mov     r9d, esi
0x1800079ef  call    WPP_SF_d
0x1800079f4  jmp     loc_180007840
```
