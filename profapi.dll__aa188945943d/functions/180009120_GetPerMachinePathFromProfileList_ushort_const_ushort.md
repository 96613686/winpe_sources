# _GetPerMachinePathFromProfileList(ushort const *,ushort * *)

- ea: `0x180009120`
- end: `0x1800091e1`
- name: `?_GetPerMachinePathFromProfileList@@YAJPEBGPEAPEAG@Z`
- size: `193`
- prototype: `__int64 __fastcall(const WCHAR *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008910`

## callees

- `0x180002484`
- `0x180005b90`
- `0x180009120`
- `0x1800091f0`

## string_xrefs

- `0x18000918a`: `minio\profapi\path.cpp`
- `0x18000917e`: `Failed to read regValue %ws`

## pseudocode

```c
__int64 __fastcall _GetPerMachinePathFromProfileList(const WCHAR *a1, unsigned __int16 **a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  unsigned int v6; // edi
  unsigned __int16 *v8; // [rsp+30h] [rbp-48h] BYREF
  __int64 v9; // [rsp+38h] [rbp-40h]
  __int64 v10; // [rsp+40h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  *a2 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v4 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::Initialize(
         (__int64)&v8,
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
         a1);
  v5 = -2147024877;
  v6 = v4;
  if ( v4 != -2147024877 )
  {
    if ( v4 >= 0 )
    {
      v5 = 0;
      *a2 = v8;
      v8 = 0;
      v10 = 0;
      v9 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x15,
        (unsigned int)"minio\\profapi\\path.cpp",
        (const char *)(unsigned int)v4,
        (int)"Failed to read regValue %ws",
        (const char *)a1);
      v5 = v6;
    }
  }
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v8);
  return v5;
}

```

## disassembly

```asm
0x180009120  mov     rax, rsp
0x180009123  push    rbx
0x180009124  push    rbp
0x180009125  push    rsi
0x180009126  push    rdi
0x180009127  sub     rsp, 58h
0x18000912b  mov     rsi, rdx
0x18000912e  mov     qword ptr [rdx], 0
0x180009135  mov     rbp, rcx
0x180009138  mov     qword ptr [rax-48h], 0
0x180009140  mov     r9, rcx
0x180009143  mov     qword ptr [rax-40h], 0
0x18000914b  mov     rdx, 0FFFFFFFF80000002h
0x180009152  mov     qword ptr [rax-38h], 0
0x18000915a  lea     rcx, [rax-48h]
0x18000915e  lea     r8, aSoftwareMicros_24; "Software\\Microsoft\\Windows NT\\Curren"...
0x180009165  call    ?Initialize@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::Initialize(HKEY__ *,ushort const *,ushort const *)
0x18000916a  mov     ebx, 80070013h
0x18000916f  mov     edi, eax
0x180009171  cmp     eax, ebx
0x180009173  jz      short loc_1800091CC
0x180009175  test    eax, eax
0x180009177  jns     short loc_1800091A7
0x180009179  mov     rcx, [rsp+78h]; this
0x18000917e  lea     rax, aFailedToReadRe; "Failed to read regValue %ws"
0x180009185  mov     [rsp+78h+var_50], rbp; char *
0x18000918a  lea     r8, aMinioProfapiPa; "minio\\profapi\\path.cpp"
0x180009191  mov     r9d, edi; char *
0x180009194  mov     qword ptr [rsp+78h+var_58], rax; int
0x180009199  mov     edx, 15h; void *
0x18000919e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800091a3  mov     ebx, edi
0x1800091a5  jmp     short loc_1800091CC
0x1800091a7  mov     rax, [rsp+78h+var_48]
0x1800091ac  xor     ebx, ebx
0x1800091ae  mov     [rsi], rax
0x1800091b1  mov     [rsp+78h+var_48], 0
0x1800091ba  mov     [rsp+78h+var_38], 0
0x1800091c3  mov     [rsp+78h+var_40], 0
0x1800091cc  lea     rcx, [rsp+78h+var_48]
0x1800091d1  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800091d6  mov     eax, ebx
0x1800091d8  add     rsp, 58h
0x1800091dc  pop     rdi
0x1800091dd  pop     rsi
0x1800091de  pop     rbp
0x1800091df  pop     rbx
0x1800091e0  retn
```
