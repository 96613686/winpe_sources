# CDXGIOutput::GetDesc(DXGI_OUTPUT_DESC *)

- ea: `0x180045890`
- end: `0x180045a53`
- name: `?GetDesc@CDXGIOutput@@UEAAJPEAUDXGI_OUTPUT_DESC@@@Z`
- size: `451`
- prototype: `__int64 __fastcall(CDXGIOutput *__hidden this, struct DXGI_OUTPUT_DESC *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180086e40`

## callees

- `0x180045890`
- `0x180075fa0`
- `0x180076f20`
- `0x1800cb010`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800459aa`
- `ntdll!EtwEventWrite` at `0x180045a3d`
- `ntdll!EtwEventWrite` at `0x1800459aa`
- `ntdll!EtwEventWrite` at `0x180045a3d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDXGIOutput::GetDesc(CDXGIOutput *this, struct DXGI_OUTPUT_DESC *a2)
{
  unsigned __int64 v4; // rsi
  int v5; // eax
  unsigned int v6; // edi
  char v8; // [rsp+20h] [rbp-E0h]
  char v9; // [rsp+24h] [rbp-DCh] BYREF
  __int16 v10; // [rsp+25h] [rbp-DBh]
  char v11; // [rsp+27h] [rbp-D9h]
  _OWORD v12[10]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v13[2]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v14[2]; // [rsp+E0h] [rbp-20h] BYREF
  struct DXGI_OUTPUT_DESC *v15; // [rsp+F0h] [rbp-10h]
  __int64 v16; // [rsp+F8h] [rbp-8h]

  v13[0] = this;
  v8 = 0;
  if ( dword_180108134
    && (qword_180108120 & 0x4000000000000000LL) != 0
    && (qword_180108128 & 0x4000000000000000LL) == qword_180108128 )
  {
    v8 = 1;
    v14[0] = v13;
    v14[1] = 8;
    v16 = 96;
    if ( a2 )
      v15 = a2;
    else
      v15 = (struct DXGI_OUTPUT_DESC *)v12;
    EtwEventWrite(DXGIEtwProviderGuid_Context, IDXGIOutput_GetDesc_Start, 2, v14);
  }
  v4 = ((unsigned __int64)this + 152) & -(__int64)(this != 0);
  (**(void (__fastcall ***)(unsigned __int64))v4)(v4);
  memset_0(v12, 0, 0x98u);
  v5 = (*(__int64 (__fastcall **)(CDXGIOutput *, _OWORD *))(*(_QWORD *)this + 216LL))(this, v12);
  v6 = v5;
  LODWORD(v13[0]) = v5;
  if ( v5 >= 0 )
  {
    *(_OWORD *)a2->DeviceName = v12[0];
    *(_OWORD *)&a2->DeviceName[8] = v12[1];
    *(_OWORD *)&a2->DeviceName[16] = v12[2];
    *(_OWORD *)&a2->DeviceName[24] = v12[3];
    a2->DesktopCoordinates = (RECT)v12[4];
    *(_OWORD *)&a2->AttachedToDesktop = v12[5];
  }
  v9 = v5;
  v10 = *(_WORD *)((char *)v13 + 1);
  v11 = BYTE3(v13[0]);
  (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v4 + 8LL))(v4);
  if ( v8 )
  {
    v13[0] = &v9;
    v13[1] = 4;
    EtwEventWrite(DXGIEtwProviderGuid_Context, IDXGIOutput_GetDesc_Stop, 1, v13);
  }
  return v6;
}

```

## disassembly

```asm
0x180045890  mov     [rsp-8+arg_10], rbx
0x180045895  push    rbp
0x180045896  push    rsi
0x180045897  push    rdi
0x180045898  lea     rbp, [rsp-10h]
0x18004589d  sub     rsp, 110h
0x1800458a4  mov     rax, cs:__security_cookie
0x1800458ab  xor     rax, rsp
0x1800458ae  mov     [rbp+20h+var_20], rax
0x1800458b2  mov     rbx, rdx
0x1800458b5  mov     rdi, rcx
0x1800458b8  mov     [rbp+20h+var_50], rcx
0x1800458bc  mov     [rsp+120h+var_100], 0
0x1800458c1  cmp     cs:dword_180108134, 0
0x1800458c8  jnz     loc_1800459D1
0x1800458ce  mov     rax, rdi
0x1800458d1  lea     rcx, [rdi+98h]
0x1800458d8  neg     rax
0x1800458db  sbb     rsi, rsi
0x1800458de  and     rsi, rcx
0x1800458e1  mov     rax, [rsi]
0x1800458e4  mov     rcx, rsi
0x1800458e7  mov     rax, [rax]
0x1800458ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800458ef  xor     edx, edx; Val
0x1800458f1  mov     r8d, 98h; Size
0x1800458f7  lea     rcx, [rsp+120h+var_F0]; void *
0x1800458fc  call    memset_0
0x180045901  mov     rax, [rdi]
0x180045904  lea     rdx, [rsp+120h+var_F0]
0x180045909  mov     rcx, rdi
0x18004590c  mov     rax, [rax+0D8h]
0x180045913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045918  mov     edi, eax
0x18004591a  mov     dword ptr [rbp+20h+var_50], eax
0x18004591d  test    eax, eax
0x18004591f  js      short loc_180045955
0x180045921  movaps  xmm0, [rsp+120h+var_F0]
0x180045926  movups  xmmword ptr [rbx], xmm0
0x180045929  movaps  xmm1, [rsp+120h+var_E0]
0x18004592e  movups  xmmword ptr [rbx+10h], xmm1
0x180045932  movaps  xmm0, [rsp+120h+var_D0]
0x180045937  movups  xmmword ptr [rbx+20h], xmm0
0x18004593b  movaps  xmm1, [rsp+120h+var_C0]
0x180045940  movups  xmmword ptr [rbx+30h], xmm1
0x180045944  movaps  xmm0, [rsp+120h+var_B0]
0x180045949  movups  xmmword ptr [rbx+40h], xmm0
0x18004594d  movaps  xmm1, [rbp+20h+var_A0]
0x180045951  movups  xmmword ptr [rbx+50h], xmm1
0x180045955  mov     [rsp+120h+var_FC], dil
0x18004595a  movzx   eax, word ptr [rbp+20h+var_50+1]
0x18004595e  mov     [rsp+120h+var_FB], ax
0x180045963  mov     al, byte ptr [rbp+20h+var_50+3]
0x180045966  mov     [rsp+120h+var_F9], al
0x18004596a  mov     rax, [rsi]
0x18004596d  mov     rcx, rsi
0x180045970  mov     rax, [rax+8]
0x180045974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045979  nop
0x18004597a  cmp     [rsp+120h+var_100], 0
0x18004597f  jz      short loc_1800459B0
0x180045981  lea     rax, [rsp+120h+var_FC]
0x180045986  mov     [rbp+20h+var_50], rax
0x18004598a  mov     [rbp+20h+var_48], 4
0x180045992  lea     r9, [rbp+20h+var_50]
0x180045996  mov     r8d, 1
0x18004599c  lea     rdx, IDXGIOutput_GetDesc_Stop
0x1800459a3  mov     rcx, cs:DXGIEtwProviderGuid_Context
0x1800459aa  call    cs:__imp_EtwEventWrite
0x1800459b0  mov     eax, edi
0x1800459b2  mov     rcx, [rbp+20h+var_20]
0x1800459b6  xor     rcx, rsp; StackCookie
0x1800459b9  call    __security_check_cookie
0x1800459be  mov     rbx, [rsp+120h+arg_10]
0x1800459c6  add     rsp, 110h
0x1800459cd  pop     rdi
0x1800459ce  pop     rsi
0x1800459cf  pop     rbp
0x1800459d0  retn
0x1800459d1  mov     rdx, 4000000000000000h
0x1800459db  test    cs:qword_180108120, rdx
0x1800459e2  jz      loc_1800458CE
0x1800459e8  mov     rax, cs:qword_180108128
0x1800459ef  and     rax, rdx
0x1800459f2  cmp     rax, cs:qword_180108128
0x1800459f9  jnz     loc_1800458CE
0x1800459ff  mov     [rsp+120h+var_100], 1
0x180045a04  lea     rax, [rbp+20h+var_50]
0x180045a08  mov     [rbp+20h+var_40], rax
0x180045a0c  mov     [rbp+20h+var_38], 8
0x180045a14  mov     [rbp+20h+var_28], 60h ; '`'
0x180045a1c  test    rbx, rbx
0x180045a1f  jz      short loc_180045A48
0x180045a21  mov     [rbp+20h+var_30], rbx
0x180045a25  lea     r9, [rbp+20h+var_40]
0x180045a29  mov     r8d, 2
0x180045a2f  lea     rdx, IDXGIOutput_GetDesc_Start
0x180045a36  mov     rcx, cs:DXGIEtwProviderGuid_Context
0x180045a3d  call    cs:__imp_EtwEventWrite
0x180045a43  jmp     loc_1800458CE
0x180045a48  lea     rax, [rsp+120h+var_F0]
0x180045a4d  mov     [rbp+20h+var_30], rax
0x180045a51  jmp     short loc_180045A25
```
