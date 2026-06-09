# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800053b0`
- end: `0x18000548d`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `221`
- prototype: `__int64 __fastcall(__int64, _DWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800054a0`

## callees

- `0x1800053b0`
- `0x180009010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,Microsoft::WRL::FtmBase>::QueryInterface(
        __int64 a1,
        _DWORD *a2,
        __int64 *a3)
{
  unsigned int v3; // ebx
  __int64 v4; // rcx
  int v5; // eax

  v3 = 0;
  *a3 = 0;
  if ( *a2 )
  {
    if ( *a2 == 1847357737
      && a2[1] == *(_DWORD *)&GUID_6e1c7129_61e0_5d88_9fd4_f3ce65a05719.Data2
      && a2[2] == *(_DWORD *)GUID_6e1c7129_61e0_5d88_9fd4_f3ce65a05719.Data4
      && a2[3] == *(_DWORD *)&GUID_6e1c7129_61e0_5d88_9fd4_f3ce65a05719.Data4[4] )
    {
      *a3 = a1;
LABEL_22:
      a1 = *a3;
      goto LABEL_6;
    }
LABEL_12:
    v4 = a1 + 8;
    if ( *a2 == -1796592748 )
    {
      if ( a2[1] != *(_DWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
        || a2[2] != *(_DWORD *)GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4 )
      {
        return (unsigned int)-2147467262;
      }
      v5 = *(_DWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4[4];
    }
    else
    {
      if ( *a2 != 3
        || a2[1] != *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data2
        || a2[2] != *(_DWORD *)GUID_00000003_0000_0000_c000_000000000046.Data4 )
      {
        return (unsigned int)-2147467262;
      }
      v5 = *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data4[4];
    }
    if ( a2[3] == v5 )
    {
      *a3 = v4;
      goto LABEL_22;
    }
    return (unsigned int)-2147467262;
  }
  if ( a2[1] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
    || a2[2] != *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4
    || a2[3] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4] )
  {
    goto LABEL_12;
  }
  *a3 = a1;
LABEL_6:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  return v3;
}

```

## disassembly

```asm
0x1800053b0  push    rbx
0x1800053b2  sub     rsp, 20h
0x1800053b6  xor     ebx, ebx
0x1800053b8  mov     [r8], rbx
0x1800053bb  cmp     [rdx], ebx
0x1800053bd  jnz     short loc_1800053F4
0x1800053bf  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x1800053c5  cmp     [rdx+4], eax
0x1800053c8  jnz     short loc_180005422
0x1800053ca  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x1800053d0  cmp     [rdx+8], eax
0x1800053d3  jnz     short loc_180005422
0x1800053d5  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x1800053db  cmp     [rdx+0Ch], eax
0x1800053de  jnz     short loc_180005422
0x1800053e0  mov     [r8], rcx
0x1800053e3  mov     rax, [rcx]
0x1800053e6  mov     rax, [rax+8]
0x1800053ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053ef  jmp     loc_180005485
0x1800053f4  cmp     dword ptr [rdx], 6E1C7129h
0x1800053fa  jnz     short loc_180005422
0x1800053fc  mov     eax, dword ptr cs:_GUID_6e1c7129_61e0_5d88_9fd4_f3ce65a05719.Data2
0x180005402  cmp     [rdx+4], eax
0x180005405  jnz     short loc_180005422
0x180005407  mov     eax, dword ptr cs:_GUID_6e1c7129_61e0_5d88_9fd4_f3ce65a05719.Data4
0x18000540d  cmp     [rdx+8], eax
0x180005410  jnz     short loc_180005422
0x180005412  mov     eax, dword ptr cs:_GUID_6e1c7129_61e0_5d88_9fd4_f3ce65a05719.Data4+4
0x180005418  cmp     [rdx+0Ch], eax
0x18000541b  jnz     short loc_180005422
0x18000541d  mov     [r8], rcx
0x180005420  jmp     short loc_180005478
0x180005422  add     rcx, 8
0x180005426  cmp     dword ptr [rdx], 94EA2B94h
0x18000542c  jnz     short loc_18000544C
0x18000542e  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
0x180005434  cmp     [rdx+4], eax
0x180005437  jnz     short loc_180005480
0x180005439  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4
0x18000543f  cmp     [rdx+8], eax
0x180005442  jnz     short loc_180005480
0x180005444  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4+4
0x18000544a  jmp     short loc_18000546D
0x18000544c  cmp     dword ptr [rdx], 3
0x18000544f  jnz     short loc_180005480
0x180005451  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data2
0x180005457  cmp     [rdx+4], eax
0x18000545a  jnz     short loc_180005480
0x18000545c  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4
0x180005462  cmp     [rdx+8], eax
0x180005465  jnz     short loc_180005480
0x180005467  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4+4
0x18000546d  cmp     [rdx+0Ch], eax
0x180005470  jnz     short loc_180005480
0x180005472  mov     rax, r8
0x180005475  mov     [rax], rcx
0x180005478  mov     rcx, [r8]
0x18000547b  jmp     loc_1800053E3
0x180005480  mov     ebx, 80004002h
0x180005485  mov     eax, ebx
0x180005487  add     rsp, 20h
0x18000548b  pop     rbx
0x18000548c  retn
```
