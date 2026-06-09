# NGENService::GenerateRandomName(ushort * *)

- ea: `0x180004580`
- end: `0x1800046c3`
- name: `?GenerateRandomName@NGENService@@YAJPEAPEAG@Z`
- size: `323`
- prototype: `__int64 __fastcall(NGENService *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800046c4`

## callees

- `0x180001e8c`
- `0x180004580`
- `0x180030ab8`
- `0x180030d84`
- `0x180035940`
- `0x18003dc30`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180004693`
- `KERNEL32!HeapFree` at `0x180004693`
- `KERNEL32!GetProcessHeap` at `0x18000467e`
- `KERNEL32!GetProcessHeap` at `0x18000467e`
- `ole32!CoCreateGuid` at `0x1800045fc`
- `ole32!CoCreateGuid` at `0x1800045fc`
- `OLEAUT32!__imp_SysAllocString` at `0x180004646`
- `OLEAUT32!__imp_SysAllocString` at `0x180004646`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall NGENService::GenerateRandomName(NGENService *this, unsigned __int16 **a2)
{
  unsigned int v2; // r8d
  const WCHAR *v3; // rax
  unsigned int v4; // ebx
  OLECHAR *v5; // rdi
  HANDLE ProcessHeap; // rax
  struct _GUID v8; // [rsp+28h] [rbp-E0h] BYREF
  GUID pguid_8; // [rsp+38h] [rbp-D0h] BYREF
  int v10; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v11; // [rsp+4Ch] [rbp-BCh]
  OLECHAR *psz; // [rsp+58h] [rbp-B0h]
  __int16 v13; // [rsp+60h] [rbp-A8h] BYREF
  unsigned __int16 v14[64]; // [rsp+268h] [rbp+160h] BYREF

  v11 = 512;
  psz = (OLECHAR *)&v13;
  v10 = 2;
  v13 = 0;
  SString::Set((SString *)&v10, L"Local\\");
  NGENService::g_bstrInterruptEventName = 0;
  if ( CoCreateGuid(&pguid_8) >= 0
    && (v8 = pguid_8, (unsigned int)GuidToLPWSTR(&v8, v14, v2))
    && (SString::Append((SString *)&v10, v14),
        SString::ConvertToUnicode((SString *)&v10),
        (v3 = SysAllocString(psz)) != 0) )
  {
    NGENService::g_bstrInterruptEventName = v3;
    v4 = 0;
  }
  else
  {
    v4 = -2147467259;
  }
  if ( (v11 & 0x800000000LL) != 0 )
  {
    v5 = psz;
    if ( psz )
    {
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      HeapFree(ProcessHeap, 0, v5);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180004580  mov     rax, rsp
0x180004583  mov     [rax+8], rbx
0x180004587  mov     [rax+10h], rsi
0x18000458b  mov     [rax+18h], rdi
0x18000458f  push    rbp
0x180004590  lea     rbp, [rax-1F8h]
0x180004597  sub     rsp, 2F0h
0x18000459e  mov     rax, cs:__security_cookie
0x1800045a5  xor     rax, rsp
0x1800045a8  mov     [rbp+1F0h+var_10], rax
0x1800045af  xor     esi, esi
0x1800045b1  mov     qword ptr [rsp+2F0h+var_2B0], rsi
0x1800045b6  mov     qword ptr [rsp+44h], 200h
0x1800045bf  mov     [rsp+2F0h+psz], rsi
0x1800045c4  lea     rax, [rsp+2F0h+var_298]
0x1800045c9  mov     [rsp+2F0h+psz], rax
0x1800045ce  mov     [rsp+2F0h+var_2B0], 2
0x1800045d6  mov     rax, [rsp+2F0h+psz]
0x1800045db  mov     [rax], si
0x1800045de  lea     rdx, aLocal; "Local\\"
0x1800045e5  lea     rcx, [rsp+2F0h+var_2B0]; this
0x1800045ea  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x1800045ef  nop
0x1800045f0  mov     cs:?g_bstrInterruptEventName@NGENService@@3PEAGEA, rsi; ushort * NGENService::g_bstrInterruptEventName
0x1800045f7  lea     rcx, [rsp+2F0h+pguid+8]; pguid
0x1800045fc  call    cs:__imp_CoCreateGuid
0x180004602  test    eax, eax
0x180004604  js      short loc_18000465C
0x180004606  movaps  xmm0, xmmword ptr [rsp+2F0h+pguid+8]
0x18000460b  movdqa  xmmword ptr [rsp+2F0h+var_2D8.Data4], xmm0
0x180004611  lea     rdx, [rbp+1F0h+var_90]; unsigned __int16 *
0x180004618  lea     rcx, [rsp+2F0h+var_2D8.Data4]; struct _GUID
0x18000461d  call    ?GuidToLPWSTR@@YAHU_GUID@@PEAGK@Z; GuidToLPWSTR(_GUID,ushort *,ulong)
0x180004622  test    eax, eax
0x180004624  jz      short loc_18000465C
0x180004626  lea     rdx, [rbp+1F0h+var_90]; unsigned __int16 *
0x18000462d  lea     rcx, [rsp+2F0h+var_2B0]; this
0x180004632  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x180004637  lea     rcx, [rsp+2F0h+var_2B0]; this
0x18000463c  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180004641  mov     rcx, [rsp+2F0h+psz]; psz
0x180004646  call    cs:__imp_SysAllocString
0x18000464c  test    rax, rax
0x18000464f  jz      short loc_18000465C
0x180004651  mov     cs:?g_bstrInterruptEventName@NGENService@@3PEAGEA, rax; ushort * NGENService::g_bstrInterruptEventName
0x180004658  mov     ebx, esi
0x18000465a  jmp     short loc_180004661
0x18000465c  mov     ebx, 80004005h
0x180004661  test    byte ptr [rsp+2F0h+var_2A8], 8
0x180004666  jz      short loc_180004699
0x180004668  mov     rdi, [rsp+2F0h+psz]
0x18000466d  test    rdi, rdi
0x180004670  jz      short loc_180004699
0x180004672  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180004679  test    rax, rax
0x18000467c  jnz     short loc_18000468B
0x18000467e  call    cs:__imp_GetProcessHeap
0x180004684  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18000468b  mov     r8, rdi; lpMem
0x18000468e  xor     edx, edx; dwFlags
0x180004690  mov     rcx, rax; hHeap
0x180004693  call    cs:__imp_HeapFree
0x180004699  mov     eax, ebx
0x18000469b  mov     rcx, [rbp+1F0h+var_10]
0x1800046a2  xor     rcx, rsp; StackCookie
0x1800046a5  call    __security_check_cookie
0x1800046aa  lea     r11, [rsp+2F0h+var_s0]
0x1800046b2  mov     rbx, [r11+10h]
0x1800046b6  mov     rsi, [r11+18h]
0x1800046ba  mov     rdi, [r11+20h]
0x1800046be  mov     rsp, r11
0x1800046c1  pop     rbp
0x1800046c2  retn
```
