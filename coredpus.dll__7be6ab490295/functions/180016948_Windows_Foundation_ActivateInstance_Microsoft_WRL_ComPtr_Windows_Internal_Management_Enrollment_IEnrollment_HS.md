# Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>>)

- ea: `0x180016948`
- end: `0x1800169e7`
- name: `??$ActivateInstance@V?$ComPtr@UIEnrollment@Enrollment@Management@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIEnrollment@Enrollment@Management@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z`
- size: `159`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180011b00`

## callees

- `0x180011d6c`
- `0x180015c6f`
- `0x180016948`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180016978`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180016978`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>>(
        __int64 a1,
        __int64 *a2)
{
  int v4; // edi
  __int64 v6; // [rsp+38h] [rbp+10h] BYREF

  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
  *a2 = 0;
  v6 = 0;
  v4 = RoActivateInstance(a1, &v6);
  if ( v4 >= 0 )
  {
    if ( !memcmp_0(&GUID_9cb302b2_e79d_4beb_84c7_3abcb992df4e, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      *a2 = v6;
    }
    else
    {
      v4 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v6)(
             v6,
             &GUID_9cb302b2_e79d_4beb_84c7_3abcb992df4e,
             a2);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180016948  mov     [rsp+arg_0], rbx
0x18001694d  push    rdi
0x18001694e  sub     rsp, 20h
0x180016952  mov     rbx, rdx
0x180016955  mov     rdi, rcx
0x180016958  mov     rcx, rdx
0x18001695b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180016960  mov     qword ptr [rbx], 0
0x180016967  mov     [rsp+28h+arg_8], 0
0x180016970  lea     rdx, [rsp+28h+arg_8]
0x180016975  mov     rcx, rdi
0x180016978  call    cs:__imp_RoActivateInstance
0x18001697f  nop     dword ptr [rax+rax+00h]
0x180016984  mov     edi, eax
0x180016986  test    eax, eax
0x180016988  js      short loc_1800169D9
0x18001698a  mov     r8d, 10h; Size
0x180016990  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180016997  lea     rcx, _GUID_9cb302b2_e79d_4beb_84c7_3abcb992df4e; Buf1
0x18001699e  call    memcmp_0
0x1800169a3  mov     rcx, [rsp+28h+arg_8]
0x1800169a8  test    eax, eax
0x1800169aa  jnz     short loc_1800169B1
0x1800169ac  mov     [rbx], rcx
0x1800169af  jmp     short loc_1800169D9
0x1800169b1  mov     rax, [rcx]
0x1800169b4  mov     r8, rbx
0x1800169b7  lea     rdx, _GUID_9cb302b2_e79d_4beb_84c7_3abcb992df4e
0x1800169be  mov     rax, [rax]
0x1800169c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169c6  mov     edi, eax
0x1800169c8  mov     rcx, [rsp+28h+arg_8]
0x1800169cd  mov     rax, [rcx]
0x1800169d0  mov     rax, [rax+10h]
0x1800169d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169d9  mov     eax, edi
0x1800169db  mov     rbx, [rsp+28h+arg_0]
0x1800169e0  add     rsp, 20h
0x1800169e4  pop     rdi
0x1800169e5  retn
```
