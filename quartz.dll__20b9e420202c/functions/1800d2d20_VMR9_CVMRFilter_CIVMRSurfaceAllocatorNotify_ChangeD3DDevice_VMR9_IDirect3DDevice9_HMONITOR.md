# VMR9::CVMRFilter::CIVMRSurfaceAllocatorNotify::ChangeD3DDevice(VMR9::IDirect3DDevice9 *,HMONITOR__ *)

- ea: `0x1800d2d20`
- end: `0x1800d2f25`
- name: `?ChangeD3DDevice@CIVMRSurfaceAllocatorNotify@CVMRFilter@VMR9@@UEAAJPEAUIDirect3DDevice9@3@PEAUHMONITOR__@@@Z`
- size: `517`
- prototype: `int(VMR9::CVMRFilter::CIVMRSurfaceAllocatorNotify *__hidden this, struct IDirect3DDevice9 *, HMONITOR)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x1800300cc`
- `0x1800388a0`
- `0x180039250`
- `0x1800d2d20`
- `0x1800d52f0`
- `0x18015e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800d2ed5`
- `KERNEL32!LeaveCriticalSection` at `0x1800d2ee8`
- `KERNEL32!LeaveCriticalSection` at `0x1800d2ed5`
- `KERNEL32!LeaveCriticalSection` at `0x1800d2ee8`
- `KERNEL32!EnterCriticalSection` at `0x1800d2d60`
- `KERNEL32!EnterCriticalSection` at `0x1800d2d60`
- `ole32!CoTaskMemFree` at `0x1800d2e9d`
- `ole32!CoTaskMemFree` at `0x1800d2e9d`
- `ole32!CoTaskMemAlloc` at `0x1800d2dc0`
- `ole32!CoTaskMemAlloc` at `0x1800d2dc0`

## pseudocode

```c
__int64 __fastcall VMR9::CVMRFilter::CIVMRSurfaceAllocatorNotify::ChangeD3DDevice(
        VMR9::CVMRFilter::CIVMRSurfaceAllocatorNotify *this,
        struct IDirect3DDevice9 *a2,
        HMONITOR a3)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  int v7; // ebp
  int v8; // edi
  _QWORD *v9; // rax
  _QWORD *v10; // r12
  int v11; // r13d
  __int64 v12; // r15
  __int64 v13; // rcx
  __int64 v14; // rsi
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rax
  int i; // edi
  __int64 v19; // rcx
  int v21; // [rsp+20h] [rbp-D8h]
  _QWORD v22[16]; // [rsp+30h] [rbp-C8h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)(*((_QWORD *)this + 2) + 376LL);
  EnterCriticalSection(v4);
  if ( a2 && a3 )
  {
    v7 = VMR9::CVMRFilter::SetD3DDeviceWorker(*((VMR9::CVMRFilter **)this + 2), a2, a3);
    if ( v7 >= 0 )
    {
      memset_0(v22, 0, sizeof(v22));
      v8 = *(_DWORD *)(*((_QWORD *)this + 2) + 572LL);
      v21 = v8;
      v9 = CoTaskMemAlloc((unsigned int)(8 * v8));
      v10 = v9;
      if ( v9 )
      {
        memset_0(v9, 0, (unsigned int)(8 * v8));
        v11 = 0;
        v12 = 0;
        if ( v8 <= 0 )
          goto LABEL_14;
        do
        {
          if ( !v7 )
          {
            v13 = *(_QWORD *)(*((_QWORD *)this + 2) + 8 * v12 + 248);
            if ( *(_QWORD *)(v13 + 48) )
            {
              v14 = v11;
              v15 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64))(v13 + 24))(
                      v13 + 24,
                      &IID_IPin,
                      (__int64)&v10[v11]);
              v16 = *((_QWORD *)this + 2);
              v7 = v15;
              v17 = v10[v11++];
              v8 = v21;
              v22[v14] = v17;
              *(_DWORD *)(v16 + 660) |= 1 << *(_DWORD *)(*(_QWORD *)(v16 + 8 * v12 + 248) + 696LL);
            }
          }
          v12 = (unsigned int)(v12 + 1);
        }
        while ( (int)v12 < v8 );
        if ( v11 <= 0 )
        {
LABEL_14:
          CoTaskMemFree(v10);
        }
        else
        {
          CBaseFilter::NotifyEvent(*((CBaseFilter **)this + 2), 22, (__int64)v10, v11);
          for ( i = 0; i < v11; ++i )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v22[i] + 16LL))(v22[i]);
        }
        if ( v7 >= 0 )
        {
          v19 = *(_QWORD *)(*((_QWORD *)this + 2) + 496LL);
          if ( v19 )
            v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 64LL))(v19);
        }
      }
      else
      {
        v7 = -2147024882;
      }
    }
    LeaveCriticalSection(v4);
    return (unsigned int)v7;
  }
  else
  {
    LeaveCriticalSection(v4);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800d2d20  mov     [rsp+arg_18], rbx
0x1800d2d25  push    rbp
0x1800d2d26  push    rsi
0x1800d2d27  push    rdi
0x1800d2d28  push    r12
0x1800d2d2a  push    r13
0x1800d2d2c  push    r14
0x1800d2d2e  push    r15
0x1800d2d30  sub     rsp, 0C0h
0x1800d2d37  mov     rax, cs:__security_cookie
0x1800d2d3e  xor     rax, rsp
0x1800d2d41  mov     [rsp+0F8h+var_48], rax
0x1800d2d49  mov     rbx, [rcx+10h]
0x1800d2d4d  mov     r14, rcx
0x1800d2d50  add     rbx, 178h
0x1800d2d57  mov     rdi, r8
0x1800d2d5a  mov     rcx, rbx; lpCriticalSection
0x1800d2d5d  mov     rsi, rdx
0x1800d2d60  call    cs:__imp_EnterCriticalSection
0x1800d2d67  nop     dword ptr [rax+rax+00h]
0x1800d2d6c  test    rsi, rsi
0x1800d2d6f  jz      loc_1800D2EE5
0x1800d2d75  test    rdi, rdi
0x1800d2d78  jz      loc_1800D2EE5
0x1800d2d7e  mov     rcx, [r14+10h]; this
0x1800d2d82  mov     r8, rdi; hMonitor
0x1800d2d85  mov     rdx, rsi; struct IDirect3DDevice9 *
0x1800d2d88  call    ?SetD3DDeviceWorker@CVMRFilter@VMR9@@AEAAJPEAUIDirect3DDevice9@2@PEAUHMONITOR__@@@Z; VMR9::CVMRFilter::SetD3DDeviceWorker(VMR9::IDirect3DDevice9 *,HMONITOR__ *)
0x1800d2d8d  mov     ebp, eax
0x1800d2d8f  test    eax, eax
0x1800d2d91  js      loc_1800D2ED2
0x1800d2d97  xor     edx, edx; Val
0x1800d2d99  lea     rcx, [rsp+0F8h+var_C8]; void *
0x1800d2d9e  mov     r8d, 80h; Size
0x1800d2da4  call    memset_0
0x1800d2da9  mov     rcx, [r14+10h]
0x1800d2dad  mov     edi, [rcx+23Ch]
0x1800d2db3  mov     [rsp+0F8h+var_D8], edi
0x1800d2db7  lea     ecx, ds:0[rdi*8]; cb
0x1800d2dbe  mov     esi, ecx
0x1800d2dc0  call    cs:__imp_CoTaskMemAlloc
0x1800d2dc7  nop     dword ptr [rax+rax+00h]
0x1800d2dcc  mov     r12, rax
0x1800d2dcf  test    rax, rax
0x1800d2dd2  jz      loc_1800D2ECD
0x1800d2dd8  mov     r8d, esi; Size
0x1800d2ddb  xor     edx, edx; Val
0x1800d2ddd  mov     rcx, rax; void *
0x1800d2de0  call    memset_0
0x1800d2de5  xor     r13d, r13d
0x1800d2de8  xor     r15d, r15d
0x1800d2deb  test    edi, edi
0x1800d2ded  jle     loc_1800D2E9A
0x1800d2df3  test    ebp, ebp
0x1800d2df5  jnz     short loc_1800D2E5A
0x1800d2df7  mov     rax, [r14+10h]
0x1800d2dfb  mov     rcx, [rax+r15*8+0F8h]
0x1800d2e03  cmp     qword ptr [rcx+30h], 0
0x1800d2e08  jz      short loc_1800D2E5A
0x1800d2e0a  add     rcx, 18h
0x1800d2e0e  movsxd  rsi, r13d
0x1800d2e11  lea     rdx, IID_IPin
0x1800d2e18  mov     rax, [rcx]
0x1800d2e1b  lea     rdi, [r12+rsi*8]
0x1800d2e1f  mov     r8, rdi
0x1800d2e22  mov     rax, [rax]
0x1800d2e25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2e2a  mov     rdx, [r14+10h]
0x1800d2e2e  mov     ebp, eax
0x1800d2e30  mov     rax, [rdi]
0x1800d2e33  inc     r13d
0x1800d2e36  mov     edi, [rsp+0F8h+var_D8]
0x1800d2e3a  mov     [rsp+rsi*8+0F8h+var_C8], rax
0x1800d2e3f  mov     eax, 1
0x1800d2e44  mov     rcx, [rdx+r15*8+0F8h]
0x1800d2e4c  mov     ecx, [rcx+2B8h]
0x1800d2e52  shl     eax, cl
0x1800d2e54  or      [rdx+294h], eax
0x1800d2e5a  inc     r15d
0x1800d2e5d  cmp     r15d, edi
0x1800d2e60  jl      short loc_1800D2DF3
0x1800d2e62  test    r13d, r13d
0x1800d2e65  jle     short loc_1800D2E9A
0x1800d2e67  mov     rcx, [r14+10h]; this
0x1800d2e6b  mov     r8, r12; __int64
0x1800d2e6e  movsxd  r9, r13d; __int64
0x1800d2e71  mov     edx, 16h; int
0x1800d2e76  call    ?NotifyEvent@CBaseFilter@@QEAAJJ_J0@Z; CBaseFilter::NotifyEvent(long,__int64,__int64)
0x1800d2e7b  xor     edi, edi
0x1800d2e7d  movsxd  rax, edi
0x1800d2e80  mov     rcx, [rsp+rax*8+0F8h+var_C8]
0x1800d2e85  mov     rax, [rcx]
0x1800d2e88  mov     rax, [rax+10h]
0x1800d2e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2e91  inc     edi
0x1800d2e93  cmp     edi, r13d
0x1800d2e96  jl      short loc_1800D2E7D
0x1800d2e98  jmp     short loc_1800D2EA9
0x1800d2e9a  mov     rcx, r12; pv
0x1800d2e9d  call    cs:__imp_CoTaskMemFree
0x1800d2ea4  nop     dword ptr [rax+rax+00h]
0x1800d2ea9  test    ebp, ebp
0x1800d2eab  js      short loc_1800D2ED2
0x1800d2ead  mov     rax, [r14+10h]
0x1800d2eb1  mov     rcx, [rax+1F0h]
0x1800d2eb8  test    rcx, rcx
0x1800d2ebb  jz      short loc_1800D2ED2
0x1800d2ebd  mov     rax, [rcx]
0x1800d2ec0  mov     rax, [rax+40h]
0x1800d2ec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2ec9  mov     ebp, eax
0x1800d2ecb  jmp     short loc_1800D2ED2
0x1800d2ecd  mov     ebp, 8007000Eh
0x1800d2ed2  mov     rcx, rbx; lpCriticalSection
0x1800d2ed5  call    cs:__imp_LeaveCriticalSection
0x1800d2edc  nop     dword ptr [rax+rax+00h]
0x1800d2ee1  mov     eax, ebp
0x1800d2ee3  jmp     short loc_1800D2EF9
0x1800d2ee5  mov     rcx, rbx; lpCriticalSection
0x1800d2ee8  call    cs:__imp_LeaveCriticalSection
0x1800d2eef  nop     dword ptr [rax+rax+00h]
0x1800d2ef4  mov     eax, 80070057h
0x1800d2ef9  mov     rcx, [rsp+0F8h+var_48]
0x1800d2f01  xor     rcx, rsp; StackCookie
0x1800d2f04  call    __security_check_cookie
0x1800d2f09  mov     rbx, [rsp+0F8h+arg_18]
0x1800d2f11  add     rsp, 0C0h
0x1800d2f18  pop     r15
0x1800d2f1a  pop     r14
0x1800d2f1c  pop     r13
0x1800d2f1e  pop     r12
0x1800d2f20  pop     rdi
0x1800d2f21  pop     rsi
0x1800d2f22  pop     rbp
0x1800d2f23  retn
```
