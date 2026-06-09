# CPoolAllocator::CreateAllocator(void)

- ea: `0x14000f950`
- end: `0x14000fbb3`
- name: `?CreateAllocator@CPoolAllocator@@AEAAPEAVCMMFAllocator@@XZ`
- size: `611`
- prototype: `struct CMMFAllocator *__fastcall(CPoolAllocator *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140010ebc`

## callees

- `0x140001c04`
- `0x14000ebd4`
- `0x14000ef78`
- `0x14000efc8`
- `0x14000f4c8`
- `0x14000f54c`
- `0x14000f950`
- `0x140010780`

## pseudocode

```c
struct CMMFAllocator *__fastcall CPoolAllocator::CreateAllocator(CPoolAllocator *this)
{
  __int64 v2; // rdi
  int v3; // eax
  wchar_t *v4; // rdx
  bool v5; // zf
  __int64 v6; // rdx
  const WCHAR *v7; // r15
  HANDLE v8; // rbp
  CPingPong *v9; // r14
  int v10; // eax
  __int64 v11; // r9
  struct CMMFAllocator *result; // rax
  struct CMMFAllocator *v13; // rsi
  __int64 v14; // rdx
  __int64 v15; // rcx
  PCWSTR SourceString; // [rsp+50h] [rbp+8h] BYREF
  HANDLE Handle; // [rsp+58h] [rbp+10h] BYREF

  v2 = *(_QWORD *)(*(_QWORD *)this + 64LL);
  v3 = *(_DWORD *)(v2 + 328);
  if ( v3 == -1 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 39, &WPP_664e97eed756311217f592c2f10907d7_Traceguids);
    }
    return 0;
  }
  *(_DWORD *)(v2 + 328) = v3 + 1;
  v4 = **(wchar_t ***)(v2 + 320);
  if ( !v4 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 40, &WPP_664e97eed756311217f592c2f10907d7_Traceguids);
    }
    v5 = *(_DWORD *)(v2 + 1000) == 0;
LABEL_10:
    if ( v5 )
    {
      *(_DWORD *)(v2 + 1000) = 1;
      v6 = 3;
LABEL_31:
      ReportAllocationEvent(*(_QWORD *)this, v6, 0, *(unsigned int *)(v2 + 328));
      return 0;
    }
    return 0;
  }
  if ( !*((_QWORD *)this + 5) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 41, &WPP_664e97eed756311217f592c2f10907d7_Traceguids);
    }
    goto LABEL_29;
  }
  v7 = 0;
  v8 = 0;
  v9 = 0;
  SourceString = 0;
  v5 = *((_DWORD *)this + 12) == 512;
  Handle = 0;
  if ( v5 )
  {
    v9 = ACpCreateBitmap(*(struct _DEVICE_OBJECT **)this, v4, (wchar_t **)&SourceString, &Handle);
    v10 = *(_DWORD *)(v2 + 1000);
    if ( !v9 )
    {
      v5 = v10 == 0;
      goto LABEL_10;
    }
    if ( v10 )
    {
      v11 = *(unsigned int *)(v2 + 328);
      *(_DWORD *)(v2 + 1000) = 0;
      ReportAllocationEvent(*(_QWORD *)this, 3, 1, v11);
    }
    v8 = Handle;
    if ( ACpWritePingPong(v9, Handle) < 0 )
    {
      ACpCleanupBitmap(v9, SourceString, v8);
      return 0;
    }
    v7 = SourceString;
  }
  v13 = CMMFAllocator::Create(this, *((wchar_t **)this + 5), 0);
  if ( !v13 )
  {
    CSMAllocator::ReleaseFreeHeaps(*(CSMAllocator **)(v2 + 320));
    v13 = CMMFAllocator::Create(this, *((wchar_t **)this + 5), 0);
    if ( !v13 )
    {
      if ( *((_DWORD *)this + 12) == 512 )
        ACpCleanupBitmap(v9, v7, v8);
LABEL_29:
      if ( !*((_DWORD *)this + 13) )
      {
        v6 = *((unsigned int *)this + 14);
        *((_DWORD *)this + 13) = 1;
        goto LABEL_31;
      }
      return 0;
    }
  }
  if ( *((_DWORD *)this + 13) )
  {
    v14 = *((unsigned int *)this + 14);
    v15 = *(_QWORD *)this;
    *((_DWORD *)this + 13) = 0;
    ReportAllocationEvent(v15, v14, 1, *(unsigned int *)(v2 + 328));
  }
  *((_QWORD *)v13 + 16) = v9;
  result = v13;
  *((_QWORD *)v13 + 10) = v7;
  *((_QWORD *)v13 + 17) = v8;
  return result;
}

```

## disassembly

```asm
0x14000f950  mov     [rsp+arg_10], rbx
0x14000f955  push    rbp
0x14000f956  push    rsi
0x14000f957  push    rdi
0x14000f958  push    r14
0x14000f95a  push    r15
0x14000f95c  sub     rsp, 20h
0x14000f960  mov     rax, [rcx]
0x14000f963  mov     rbx, rcx
0x14000f966  mov     rdi, [rax+40h]
0x14000f96a  mov     eax, [rdi+148h]
0x14000f970  cmp     eax, 0FFFFFFFFh
0x14000f973  jnz     short loc_14000F9B1
0x14000f975  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f97c  lea     rax, WPP_GLOBAL_Control
0x14000f983  cmp     rcx, rax
0x14000f986  jz      loc_14000FAE3
0x14000f98c  mov     eax, [rcx+6Ch]
0x14000f98f  test    al, 1
0x14000f991  jz      loc_14000FAE3
0x14000f997  mov     rcx, [rcx+58h]
0x14000f99b  lea     r8, WPP_664e97eed756311217f592c2f10907d7_Traceguids
0x14000f9a2  mov     edx, 27h ; '''
0x14000f9a7  call    WPP_SF_
0x14000f9ac  jmp     loc_14000FAE3
0x14000f9b1  inc     eax
0x14000f9b3  mov     [rdi+148h], eax
0x14000f9b9  mov     rax, [rdi+140h]
0x14000f9c0  mov     rdx, [rax]; wchar_t *
0x14000f9c3  test    rdx, rdx
0x14000f9c6  jnz     short loc_14000FA18
0x14000f9c8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f9cf  lea     rax, WPP_GLOBAL_Control
0x14000f9d6  cmp     rcx, rax
0x14000f9d9  jz      short loc_14000F9F7
0x14000f9db  mov     eax, [rcx+6Ch]
0x14000f9de  test    al, 1
0x14000f9e0  jz      short loc_14000F9F7
0x14000f9e2  mov     rcx, [rcx+58h]
0x14000f9e6  lea     r8, WPP_664e97eed756311217f592c2f10907d7_Traceguids
0x14000f9ed  mov     edx, 28h ; '('
0x14000f9f2  call    WPP_SF_
0x14000f9f7  cmp     dword ptr [rdi+3E8h], 0
0x14000f9fe  jnz     loc_14000FAE3
0x14000fa04  mov     dword ptr [rdi+3E8h], 1
0x14000fa0e  mov     edx, 3
0x14000fa13  jmp     loc_14000FB50
0x14000fa18  cmp     qword ptr [rcx+28h], 0
0x14000fa1d  jnz     short loc_14000FA5B
0x14000fa1f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fa26  lea     rax, WPP_GLOBAL_Control
0x14000fa2d  cmp     rcx, rax
0x14000fa30  jz      loc_14000FB40
0x14000fa36  mov     eax, [rcx+6Ch]
0x14000fa39  test    al, 1
0x14000fa3b  jz      loc_14000FB40
0x14000fa41  mov     rcx, [rcx+58h]
0x14000fa45  lea     r8, WPP_664e97eed756311217f592c2f10907d7_Traceguids
0x14000fa4c  mov     edx, 29h ; ')'
0x14000fa51  call    WPP_SF_
0x14000fa56  jmp     loc_14000FB40
0x14000fa5b  xor     r15d, r15d
0x14000fa5e  xor     ebp, ebp
0x14000fa60  xor     r14d, r14d
0x14000fa63  mov     [rsp+48h+SourceString], r15
0x14000fa68  cmp     dword ptr [rcx+30h], 200h
0x14000fa6f  mov     [rsp+48h+Handle], rbp
0x14000fa74  jnz     short loc_14000FAEF
0x14000fa76  mov     rcx, [rcx]; struct _DEVICE_OBJECT *
0x14000fa79  lea     r9, [rsp+48h+Handle]; void **
0x14000fa7e  lea     r8, [rsp+48h+SourceString]; wchar_t **
0x14000fa83  call    ?ACpCreateBitmap@@YAPEAVCPingPong@@PEAU_DEVICE_OBJECT@@PEB_WPEAPEA_WPEAPEAX@Z; ACpCreateBitmap(_DEVICE_OBJECT *,wchar_t const *,wchar_t * *,void * *)
0x14000fa88  mov     r14, rax
0x14000fa8b  mov     eax, [rdi+3E8h]
0x14000fa91  test    r14, r14
0x14000fa94  jnz     short loc_14000FA9D
0x14000fa96  test    eax, eax
0x14000fa98  jmp     loc_14000F9FE
0x14000fa9d  test    eax, eax
0x14000fa9f  jz      short loc_14000FABF
0x14000faa1  mov     r9d, [rdi+148h]
0x14000faa8  mov     edx, 3
0x14000faad  mov     [rdi+3E8h], ebp
0x14000fab3  mov     rcx, [rbx]
0x14000fab6  lea     r8d, [rdx-2]
0x14000faba  call    ?ReportAllocationEvent@@YAJPEAU_DEVICE_OBJECT@@W4ACPoolType@@HK@Z; ReportAllocationEvent(_DEVICE_OBJECT *,ACPoolType,int,ulong)
0x14000fabf  mov     rbp, [rsp+48h+Handle]
0x14000fac4  mov     rcx, r14; struct CPingPong *
0x14000fac7  mov     rdx, rbp; void *
0x14000faca  call    ?ACpWritePingPong@@YAJPEAVCPingPong@@PEAX@Z; ACpWritePingPong(CPingPong *,void *)
0x14000facf  test    eax, eax
0x14000fad1  jns     short loc_14000FAEA
0x14000fad3  mov     rdx, [rsp+48h+SourceString]; SourceString
0x14000fad8  mov     r8, rbp; Handle
0x14000fadb  mov     rcx, r14; this
0x14000fade  call    ACpCleanupBitmap
0x14000fae3  xor     eax, eax
0x14000fae5  jmp     loc_14000FBA1
0x14000faea  mov     r15, [rsp+48h+SourceString]
0x14000faef  mov     rdx, [rbx+28h]; wchar_t *
0x14000faf3  xor     r8d, r8d; int
0x14000faf6  mov     rcx, rbx; struct CPoolAllocator *
0x14000faf9  call    ?Create@CMMFAllocator@@SAPEAV1@PEAVCPoolAllocator@@PEB_WH@Z; CMMFAllocator::Create(CPoolAllocator *,wchar_t const *,int)
0x14000fafe  mov     rsi, rax
0x14000fb01  test    rax, rax
0x14000fb04  jnz     short loc_14000FB67
0x14000fb06  mov     rcx, [rdi+140h]; this
0x14000fb0d  call    ?ReleaseFreeHeaps@CSMAllocator@@QEAAXXZ; CSMAllocator::ReleaseFreeHeaps(void)
0x14000fb12  mov     rdx, [rbx+28h]; wchar_t *
0x14000fb16  xor     r8d, r8d; int
0x14000fb19  mov     rcx, rbx; struct CPoolAllocator *
0x14000fb1c  call    ?Create@CMMFAllocator@@SAPEAV1@PEAVCPoolAllocator@@PEB_WH@Z; CMMFAllocator::Create(CPoolAllocator *,wchar_t const *,int)
0x14000fb21  mov     rsi, rax
0x14000fb24  test    rax, rax
0x14000fb27  jnz     short loc_14000FB67
0x14000fb29  cmp     dword ptr [rbx+30h], 200h
0x14000fb30  jnz     short loc_14000FB40
0x14000fb32  mov     r8, rbp; Handle
0x14000fb35  mov     rdx, r15; SourceString
0x14000fb38  mov     rcx, r14; this
0x14000fb3b  call    ACpCleanupBitmap
0x14000fb40  cmp     dword ptr [rbx+34h], 0
0x14000fb44  jnz     short loc_14000FAE3
0x14000fb46  mov     edx, [rbx+38h]
0x14000fb49  mov     dword ptr [rbx+34h], 1
0x14000fb50  mov     r9d, [rdi+148h]
0x14000fb57  xor     r8d, r8d
0x14000fb5a  mov     rcx, [rbx]
0x14000fb5d  call    ?ReportAllocationEvent@@YAJPEAU_DEVICE_OBJECT@@W4ACPoolType@@HK@Z; ReportAllocationEvent(_DEVICE_OBJECT *,ACPoolType,int,ulong)
0x14000fb62  jmp     loc_14000FAE3
0x14000fb67  cmp     dword ptr [rbx+34h], 0
0x14000fb6b  jz      short loc_14000FB8C
0x14000fb6d  mov     edx, [rbx+38h]
0x14000fb70  mov     r8d, 1
0x14000fb76  mov     rcx, [rbx]
0x14000fb79  mov     dword ptr [rbx+34h], 0
0x14000fb80  mov     r9d, [rdi+148h]
0x14000fb87  call    ?ReportAllocationEvent@@YAJPEAU_DEVICE_OBJECT@@W4ACPoolType@@HK@Z; ReportAllocationEvent(_DEVICE_OBJECT *,ACPoolType,int,ulong)
0x14000fb8c  mov     [rsi+80h], r14
0x14000fb93  mov     rax, rsi
0x14000fb96  mov     [rsi+50h], r15
0x14000fb9a  mov     [rsi+88h], rbp
0x14000fba1  mov     rbx, [rsp+48h+arg_10]
0x14000fba6  add     rsp, 20h
0x14000fbaa  pop     r15
0x14000fbac  pop     r14
0x14000fbae  pop     rdi
0x14000fbaf  pop     rsi
0x14000fbb0  pop     rbp
0x14000fbb1  retn
```
