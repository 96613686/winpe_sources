# Microsoft::Windows::MDM::OmadmClient::OmadmSessionManager::InitServerSession(Microsoft::Windows::MDM::OmadmClient::RegKeyInfo &)

- ea: `0x140040010`
- end: `0x1400400bb`
- name: `?InitServerSession@OmadmSessionManager@OmadmClient@MDM@Windows@Microsoft@@UEAAJAEAURegKeyInfo@2345@@Z`
- size: `171`
- prototype: `int(Microsoft::Windows::MDM::OmadmClient::OmadmSessionManager *__hidden this, struct Microsoft::Windows::MDM::OmadmClient::RegKeyInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000b0f4`
- `0x140040010`

## import_xrefs

- `DMCmnUtils!CopyString` at `0x140040056`
- `DMCmnUtils!CopyString` at `0x140040056`
- `ntdll!RtlIsStateSeparationEnabled` at `0x14004002f`
- `ntdll!RtlIsStateSeparationEnabled` at `0x14004002f`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::OmadmSessionManager::InitServerSession(
        Microsoft::Windows::MDM::OmadmClient::OmadmSessionManager *this,
        struct Microsoft::Windows::MDM::OmadmClient::RegKeyInfo *a2)
{
  char IsStateSeparationEnabled; // al
  const unsigned __int16 *v4; // rcx
  int v5; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *((_BYTE *)this + 8) = 1;
  *(_DWORD *)a2 = 0;
  *((_QWORD *)a2 + 1) = -2147483646;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(this);
  v4 = L"OSData\\Software\\Microsoft\\Provisioning\\OMADM";
  if ( !IsStateSeparationEnabled )
    v4 = L"Software\\Microsoft\\Provisioning\\OMADM";
  v5 = CopyString(v4, 0xFFFFFFFF, (unsigned __int16 **)a2 + 2);
  v6 = v5;
  if ( v5 >= 0 )
  {
    *((_QWORD *)a2 + 4) = 0;
    *((_QWORD *)a2 + 3) = L"SessionModelessUIActive";
    *((_QWORD *)a2 + 5) = 0;
    *((_QWORD *)a2 + 6) = 0;
    *((_DWORD *)a2 + 14) = 1;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C9,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\omadmsessionmanager.cpp",
      (const char *)(unsigned int)v5,
      v8);
  }
  return v6;
}

```

## disassembly

```asm
0x140040010  mov     [rsp+arg_0], rbx
0x140040015  push    rdi; int
0x140040016  sub     rsp, 20h
0x14004001a  mov     byte ptr [rcx+8], 1
0x14004001e  mov     rdi, rdx
0x140040021  mov     dword ptr [rdx], 0
0x140040027  mov     qword ptr [rdx+8], 0FFFFFFFF80000002h
0x14004002f  call    cs:__imp_RtlIsStateSeparationEnabled
0x140040036  nop     dword ptr [rax+rax+00h]
0x14004003b  lea     rdx, SubKey; "Software\\Microsoft\\Provisioning\\OMAD"...
0x140040042  test    al, al
0x140040044  lea     rcx, aOsdataSoftware_8; "OSData\\Software\\Microsoft\\Provisioni"...
0x14004004b  cmovz   rcx, rdx
0x14004004f  lea     r8, [rdi+10h]
0x140040053  or      edx, 0FFFFFFFFh
0x140040056  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x14004005d  nop     dword ptr [rax+rax+00h]
0x140040062  mov     ebx, eax
0x140040064  test    eax, eax
0x140040066  jns     short loc_140040083
0x140040068  mov     rcx, [rsp+28h]; this
0x14004006d  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x140040074  mov     r9d, eax; char *
0x140040077  mov     edx, 1C9h; void *
0x14004007c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140040081  jmp     short loc_1400400AD
0x140040083  lea     rax, ValueName; "SessionModelessUIActive"
0x14004008a  mov     qword ptr [rdi+20h], 0
0x140040092  mov     [rdi+18h], rax
0x140040096  mov     qword ptr [rdi+28h], 0
0x14004009e  mov     qword ptr [rdi+30h], 0
0x1400400a6  mov     dword ptr [rdi+38h], 1
0x1400400ad  mov     eax, ebx
0x1400400af  mov     rbx, [rsp+28h+arg_0]
0x1400400b4  add     rsp, 20h
0x1400400b8  pop     rdi
0x1400400b9  retn
```
