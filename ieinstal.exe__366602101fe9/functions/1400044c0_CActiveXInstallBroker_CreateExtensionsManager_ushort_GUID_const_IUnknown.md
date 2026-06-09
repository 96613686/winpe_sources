# CActiveXInstallBroker::CreateExtensionsManager(ushort *,_GUID const &,IUnknown * *)

- ea: `0x1400044c0`
- end: `0x140004599`
- name: `?CreateExtensionsManager@CActiveXInstallBroker@@QEAAJPEAGAEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `217`
- prototype: `int(CActiveXInstallBroker *__hidden this, unsigned __int16 *, const struct _GUID *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140007cd0`

## callees

- `0x1400044c0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14000457f`
- `KERNEL32!LeaveCriticalSection` at `0x14000457f`
- `KERNEL32!EnterCriticalSection` at `0x1400044e7`
- `KERNEL32!EnterCriticalSection` at `0x1400044e7`
- `ole32!CoCreateInstance` at `0x140004562`
- `ole32!CoCreateInstance` at `0x140004562`

## pseudocode

```c
__int64 __fastcall CActiveXInstallBroker::CreateExtensionsManager(
        CActiveXInstallBroker *this,
        unsigned __int16 *a2,
        const struct _GUID *a3,
        LPVOID *a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  unsigned int Instance; // ebx
  __int64 v10; // rdx
  int v11; // ecx
  int v12; // eax

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  if ( *(_DWORD *)this )
  {
    EnterCriticalSection(v4);
    if ( *((_DWORD *)this + 12) == 1 )
    {
      if ( a2 )
      {
        v10 = *((_QWORD *)this + 8) - (_QWORD)a2;
        do
        {
          v11 = *(unsigned __int16 *)((char *)a2 + v10);
          v12 = *a2 - v11;
          if ( v12 )
            break;
          ++a2;
        }
        while ( v11 );
        if ( !v12
          && *(_QWORD *)&CLSID_MAOAdminBroker.Data1 == *(_QWORD *)&a3->Data1
          && *(_QWORD *)CLSID_MAOAdminBroker.Data4 == *(_QWORD *)a3->Data4 )
        {
          Instance = CoCreateInstance(a3, 0, 1u, &IID_IUnknown, a4);
        }
        else
        {
          Instance = -2147024891;
        }
      }
      else
      {
        Instance = -2147024809;
      }
    }
    else
    {
      Instance = -2147019873;
    }
  }
  else
  {
    Instance = -2147024882;
  }
  if ( *(_DWORD *)this )
    LeaveCriticalSection(v4);
  return Instance;
}

```

## disassembly

```asm
0x1400044c0  push    rbx
0x1400044c2  push    rbp
0x1400044c3  push    rsi
0x1400044c4  push    rdi
0x1400044c5  push    r14
0x1400044c7  sub     rsp, 30h
0x1400044cb  cmp     dword ptr [rcx], 0
0x1400044ce  lea     rdi, [rcx+8]
0x1400044d2  mov     r14, r9
0x1400044d5  mov     rbp, r8
0x1400044d8  mov     rbx, rdx
0x1400044db  mov     rsi, rcx
0x1400044de  jz      loc_140004572
0x1400044e4  mov     rcx, rdi; lpCriticalSection
0x1400044e7  call    cs:__imp_EnterCriticalSection
0x1400044ee  nop     dword ptr [rax+rax+00h]
0x1400044f3  mov     r8d, 1; dwClsContext
0x1400044f9  cmp     [rsi+30h], r8d
0x1400044fd  jz      short loc_140004506
0x1400044ff  mov     ebx, 8007139Fh
0x140004504  jmp     short loc_140004577
0x140004506  test    rbx, rbx
0x140004509  jnz     short loc_140004512
0x14000450b  mov     ebx, 80070057h
0x140004510  jmp     short loc_140004577
0x140004512  mov     rdx, [rsi+40h]
0x140004516  sub     rdx, rbx
0x140004519  movzx   eax, word ptr [rbx]
0x14000451c  movzx   ecx, word ptr [rbx+rdx]
0x140004520  sub     eax, ecx
0x140004522  jnz     short loc_14000452C
0x140004524  add     rbx, 2
0x140004528  test    ecx, ecx
0x14000452a  jnz     short loc_140004519
0x14000452c  test    eax, eax
0x14000452e  jz      short loc_140004537
0x140004530  mov     ebx, 80070005h
0x140004535  jmp     short loc_140004577
0x140004537  mov     rax, qword ptr cs:CLSID_MAOAdminBroker.Data1
0x14000453e  cmp     rax, [rbp+0]
0x140004542  jnz     short loc_140004530
0x140004544  mov     rax, qword ptr cs:CLSID_MAOAdminBroker.Data4
0x14000454b  cmp     rax, [rbp+8]
0x14000454f  jnz     short loc_140004530
0x140004551  lea     r9, IID_IUnknown; riid
0x140004558  mov     [rsp+58h+ppv], r14; ppv
0x14000455d  xor     edx, edx; pUnkOuter
0x14000455f  mov     rcx, rbp; rclsid
0x140004562  call    cs:__imp_CoCreateInstance
0x140004569  nop     dword ptr [rax+rax+00h]
0x14000456e  mov     ebx, eax
0x140004570  jmp     short loc_140004577
0x140004572  mov     ebx, 8007000Eh
0x140004577  cmp     dword ptr [rsi], 0
0x14000457a  jz      short loc_14000458B
0x14000457c  mov     rcx, rdi; lpCriticalSection
0x14000457f  call    cs:__imp_LeaveCriticalSection
0x140004586  nop     dword ptr [rax+rax+00h]
0x14000458b  mov     eax, ebx
0x14000458d  add     rsp, 30h
0x140004591  pop     r14
0x140004593  pop     rdi
0x140004594  pop     rsi
0x140004595  pop     rbp
0x140004596  pop     rbx
0x140004597  retn
```
